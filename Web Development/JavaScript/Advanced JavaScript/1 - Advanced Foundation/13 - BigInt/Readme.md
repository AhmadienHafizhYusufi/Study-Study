# Rangkuman BigInt

## Pengantar
`BigInt` adalah tipe data primitif dalam JavaScript (ES2020) yang memungkinkan kita bekerja dengan angka integer yang sangat besar, melampaui batas maksimal `Number` (2^53 - 1). BigInt adalah solusi untuk operasi numerik dengan angka yang presisi tinggi.

## Membuat BigInt
Ada beberapa cara untuk membuat BigInt:

### 1. Dengan Suffix `n`
```javascript
const big1 = 123456789012345678901234567890n;
const big2 = 999_999_999_999_999_999_999n;
```

### 2. Menggunakan Constructor `BigInt()`
```javascript
const big = BigInt('123456789012345678901234567890');
```

### 3. Konversi dari Number
```javascript
const num = 42;
const big = BigInt(num); // 42n
```

## Operasi Aritmetika
BigInt mendukung operasi aritmetika dasar:

```javascript
const a = 10n;
const b = 3n;

console.log(a + b);  // 13n
console.log(a - b);  // 7n
console.log(a * b);  // 30n
console.log(a / b);  // 3n (pembagian integer, hasilnya 3, bukan 3.333...)
console.log(a % b);  // 1n (sisa bagi)
console.log(a ** b); // 1000n (pangkat)
```

## Perbandingan
BigInt dapat dibandingkan dengan `==` (loose equality) dan `===` (strict equality):

```javascript
const big = 10n;
const num = 10;

console.log(big == num);   // true (loose equality)
console.log(big === num);  // false (strict equality)
console.log(big > 5n);     // true
console.log(big < 20n);    // true
```

## Konversi ke Number
Konversi BigInt ke Number:

```javascript
const big = 123456789012345678901234567890n;
const num = Number(big); // Mungkin kehilangan presisi
console.log(num);
```

## Perhatian Penting
### 1. Tidak Dapat Dicampur dengan Number
```javascript
// ❌ Error
const result = 10n + 5; // TypeError

// ✅ Benar
const result = 10n + 5n; // 15n
```

### 2. Tidak Mendukung Desimal
```javascript
// ❌ Error
const decimal = 3.14n; // SyntaxError

// ✅ Hanya integer
const integer = 314n;
```

### 3. Operasi Bitwise
```javascript
const a = 10n;
const b = 3n;

console.log(a & b);  // 2n (AND)
console.log(a | b);  // 11n (OR)
console.log(a ^ b);  // 9n (XOR)
console.log(~a);     // -11n (NOT)
console.log(a >> 1n); // 5n (right shift)
console.log(a << 1n); // 20n (left shift)
```

## Kasus Penggunaan
- Kriptografi dan hashing
- Handling identitas numerik yang sangat besar (ID database)
- Kalkulasi finansial yang presisi
- Science dan engineering computations

## Kompatibilitas
BigInt adalah fitur ES2020 dan didukung di browser modern dan Node.js 12+.

BigInt sangat berguna ketika bekerja dengan angka yang melampaui batas `Number` JavaScript biasa!