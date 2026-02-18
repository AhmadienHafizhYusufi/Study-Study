# Rangkuman Object Destructuring

## Pengantar
Object destructuring adalah fitur ES6 dalam JavaScript yang memungkinkan kita mengekstrak properti dari objek dan menetapkannya ke variabel dengan cara yang lebih ringkas dan mudah dibaca. Ini mengurangi kebutuhan untuk mengakses properti objek satu per satu.

## Sintaks Dasar
Sintaks dasar object destructuring adalah:

```javascript
const { property1, property2 } = object;
```

Ini setara dengan:
```javascript
const property1 = object.property1;
const property2 = object.property2;
```

## Contoh Penggunaan
Berikut adalah contoh sederhana:

```javascript
const user = {
    name: "John",
    age: 30,
    city: "Jakarta"
};

// Destructuring
const { name, age, city } = user;

console.log(name); // John
console.log(age);  // 30
console.log(city); // Jakarta
```

Kita juga dapat menggunakan nama variabel yang berbeda:

```javascript
const { name: nama, age: umur } = user;
console.log(nama); // John
console.log(umur); // 30
```

## Default Values
Kita dapat memberikan nilai default jika properti tidak ada:

```javascript
const { name, age, country = "Indonesia" } = user;
console.log(country); // Indonesia (karena country tidak ada di objek)
```

## Nested Destructuring
Object destructuring juga dapat digunakan untuk objek bersarang:

```javascript
const person = {
    name: "Jane",
    address: {
        street: "Jl. Sudirman",
        city: "Jakarta"
    }
};

const { name, address: { street, city } } = person;
console.log(street); // Jl. Sudirman
console.log(city);   // Jakarta
```

## Rest Operator
Menggunakan rest operator untuk mengumpulkan sisa properti:

```javascript
const { name, ...rest } = user;
console.log(rest); // { age: 30, city: "Jakarta" }
```

## Dibandingkan dengan Cara Lama
Tanpa destructuring:

```javascript
const name = user.name;
const age = user.age;
const city = user.city;
```

Dengan destructuring, lebih ringkas dan bersih.

## Kapan Menggunakan
- Ketika perlu mengekstrak beberapa properti dari objek.
- Dalam parameter fungsi untuk objek sebagai argumen.
- Untuk membuat kode lebih deklaratif dan mudah dibaca.

Object destructuring adalah alat yang sangat berguna untuk menulis kode JavaScript yang lebih modern dan efisien!