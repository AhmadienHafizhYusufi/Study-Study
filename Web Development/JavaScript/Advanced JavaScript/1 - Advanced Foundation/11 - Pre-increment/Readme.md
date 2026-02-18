# Rangkuman Pre-increment

## Pengantar
Pre-increment adalah operator unary dalam JavaScript yang ditulis sebagai `++x`. Operator ini menambah nilai variabel sebesar 1 sebelum nilai tersebut digunakan dalam ekspresi. Ini berbeda dengan post-increment (`x++`) yang menambah nilai setelah digunakan.

## Sintaks
```javascript
++variable
```

## Cara Kerja
1. Nilai variabel ditambah 1 terlebih dahulu.
2. Nilai baru dikembalikan.

```javascript
let x = 5;
let y = ++x; // x menjadi 6, y menjadi 6
console.log(x); // 6
console.log(y); // 6
```

## Perbedaan dengan Post-increment
- **Pre-increment (`++x`)**: Tambah dulu, lalu kembalikan nilai baru.
- **Post-increment (`x++`)**: Kembalikan nilai lama, lalu tambah.

```javascript
let a = 5;
let b = ++a; // a = 6, b = 6

let c = 5;
let d = c++; // c = 6, d = 5
```

## Contoh Penggunaan
### Dalam Loop
```javascript
for (let i = 0; i < 5; ++i) {
    console.log(i); // 0, 1, 2, 3, 4
}
```

### Dalam Assignment
```javascript
let counter = 0;
let result = ++counter + 10; // counter = 1, result = 11
```

### Dalam Array Access
```javascript
let arr = [10, 20, 30];
let index = 0;
console.log(arr[++index]); // 20 (index menjadi 1 terlebih dahulu)
```

## Performa
Dalam JavaScript modern, pre-increment dan post-increment memiliki performa yang sama. Namun, dalam bahasa lain seperti C++, pre-increment lebih efisien untuk objek kompleks.

## Best Practices
- Gunakan pre-increment ketika Anda perlu nilai yang sudah ditambah.
- Dalam loop `for`, keduanya sama saja.
- Hindari penggunaan dalam ekspresi kompleks untuk menghindari kebingungan.

Pre-increment adalah operator yang berguna untuk operasi increment yang efisien dalam JavaScript!