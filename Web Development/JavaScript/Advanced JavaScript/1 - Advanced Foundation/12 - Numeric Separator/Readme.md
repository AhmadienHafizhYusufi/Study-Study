# Rangkuman Numeric Separator

## Pengantar
Numeric separator adalah fitur ES2021 dalam JavaScript yang memungkinkan kita menggunakan underscore (`_`) sebagai separator dalam literal angka untuk meningkatkan keterbacaan. Underscore ini hanya untuk visual dan tidak mempengaruhi nilai angka tersebut.

## Sintaks
```javascript
const number = 1_000_000; // Satu juta
const binary = 0b1010_0101; // Binary
const hex = 0xFF_01_02; // Hexadecimal
const octal = 0o1234_5670; // Octal
const float = 3.141_592_653_589; // Float
```

## Manfaat
Numeric separator membuat angka besar lebih mudah dibaca:

```javascript
// Tanpa separator (sulit dibaca)
const budget = 1000000000;
const price = 9999.99;

// Dengan separator (mudah dibaca)
const budget = 1_000_000_000;
const price = 9_999.99;
```

## Contoh Penggunaan
### Angka Besar
```javascript
const million = 1_000_000;
const billion = 1_000_000_000;
const trillion = 1_000_000_000_000;

console.log(million);  // 1000000
console.log(billion);  // 1000000000
console.log(trillion); // 1000000000000
```

### Berbagai Basis Numerik
```javascript
// Binary
const binary = 0b0011_1010; // 58 dalam desimal

// Hexadecimal
const hex = 0xFF_00_00; // Warna merah dalam RGB

// Octal
const octal = 0o1234_5670;

// Float dan Scientific
const pi = 3.141_592_653;
const scientific = 1.23e1_0;
```

### Kasus Praktis
```javascript
// Harga dalam Rupiah
const hargaRp = 1_250_000;

// Ukuran file dalam bytes
const fileSize = 512_000_000; // 512 MB

// Koordinat
const latitude = 6.200_000;
const longitude = 106.816_666;
```

## Aturan Penggunaan
- Separator hanya dapat ditempatkan antara digit.
- Tidak boleh di awal atau akhir angka.
- Tidak boleh di antara tanda dan digit pertama.

```javascript
// ✅ Valid
const valid1 = 1_000_000;
const valid2 = 0xFF_00;

// ❌ Invalid
const invalid1 = _1000; // Underscore di awal
const invalid2 = 1000_; // Underscore di akhir
const invalid3 = 1__000; // Double underscore
```

## Konversi ke String
Ketika mengkonversi ke string, separator tidak disertakan:

```javascript
const num = 1_000_000;
console.log(num.toString()); // "1000000"
console.log(String(num)); // "1000000"
```

## Kompatibilitas
Numeric separator didukung di JavaScript modern (ES2021). Pastikan browser atau Node.js Anda mendukung fitur ini.

Numeric separator adalah fitur sederhana namun powerful untuk meningkatkan keterbacaan kode ketika bekerja dengan angka besar!