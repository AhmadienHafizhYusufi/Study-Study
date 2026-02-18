# Rangkuman Hoisting

## Pengantar
Hoisting adalah perilaku JavaScript di mana deklarasi variabel dan fungsi dipindahkan (secara konseptual) ke bagian atas scope mereka sebelum kode dieksekusi. Ini adalah fitur penting untuk dipahami karena dapat mempengaruhi bagaimana kode berjalan.

## Hoisting dengan `var`
Ketika menggunakan `var`, deklarasi variabel di-hoist, tetapi inisialisasi tidak:

```javascript
console.log(x); // undefined (bukan error)
var x = 5;
console.log(x); // 5
```

JavaScript menginterpretasinya sebagai:

```javascript
var x;           // Hoisting - deklarasi dipindahkan ke atas
console.log(x);  // undefined
x = 5;           // Inisialisasi tetap di tempat
console.log(x);  // 5
```

## Hoisting dengan `let` dan `const`
Variabel yang dideklarasikan dengan `let` dan `const` juga di-hoist, tetapi berada dalam "Temporal Dead Zone" (TDZ):

```javascript
console.log(y); // ReferenceError: Cannot access 'y' before initialization
let y = 10;
```

Ini lebih aman daripada `var` karena mencegah akses sebelum inisialisasi.

```javascript
// Temporal Dead Zone
// console.log(z); // ReferenceError

let z = 15;
console.log(z); // 15
```

## Hoisting dengan Fungsi
Deklarasi fungsi di-hoist sepenuhnya, termasuk body-nya:

```javascript
console.log(greet('John')); // Akan berfungsi dengan baik

function greet(name) {
    return `Halo, ${name}!`;
}
```

Namun, function expression tidak di-hoist:

```javascript
console.log(sayHi()); // TypeError: sayHi is not a function

const sayHi = function() {
    return 'Hi!';
};
```

## Hoisting dengan `const`
Sama seperti `let`, `const` berada dalam Temporal Dead Zone:

```javascript
// Temporal Dead Zone
console.log(PI); // ReferenceError

const PI = 3.14159;
```

Namun, `const` tidak dapat di-reassign:

```javascript
const name = 'John';
name = 'Jane'; // TypeError: Assignment to constant variable
```

## Contoh Praktis
### Masalah dengan `var`
```javascript
for (var i = 0; i < 3; i++) {
    setTimeout(() => {
        console.log(i); // Output: 3, 3, 3 (bukan 0, 1, 2)
    }, 100);
}

// Karena var di-hoist ke function scope
```

### Solusi dengan `let`
```javascript
for (let i = 0; i < 3; i++) {
    setTimeout(() => {
        console.log(i); // Output: 0, 1, 2 (benar)
    }, 100);
}

// let memiliki block scope, jadi setiap iterasi memiliki i sendiri
```

## Best Practices
- Hindari menggunakan `var`, gunakan `let` dan `const`.
- Deklarasikan variabel di awal block scope untuk clarity.
- Selalu inisialisasi variabel sebelum menggunakannya.
- Gunakan function declaration untuk fungsi yang dapat di-hoist penuh.

Memahami hoisting adalah kunci untuk menulis JavaScript yang pre-deterministic dan menghindari bugs yang sulit dilacak!