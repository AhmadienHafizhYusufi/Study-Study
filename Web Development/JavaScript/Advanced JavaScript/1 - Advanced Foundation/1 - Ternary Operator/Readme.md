# Rangkuman Ternary Operator

## Pengantar
Ternary operator adalah operator kondisional dalam JavaScript yang memungkinkan kita menulis pernyataan if-else dalam satu baris. Ini adalah cara singkat untuk mengevaluasi kondisi dan mengembalikan nilai berdasarkan hasilnya.

## Sintaks
Sintaks dasar ternary operator adalah:
```
condition ? expression1 : expression2
```

- `condition`: Ekspresi yang dievaluasi sebagai true atau false.
- `expression1`: Nilai yang dikembalikan jika condition bernilai true.
- `expression2`: Nilai yang dikembalikan jika condition bernilai false.

## Contoh Penggunaan
Berikut adalah contoh sederhana penggunaan ternary operator:

```javascript
let age = 18;
let canVote = age >= 18 ? "Bisa memilih" : "Belum bisa memilih";
console.log(canVote); // Output: Bisa memilih
```

Dalam contoh ini, jika `age` lebih besar atau sama dengan 18, maka `canVote` akan diisi dengan "Bisa memilih", jika tidak, "Belum bisa memilih".

## Dibandingkan dengan If-Else
Ternary operator dapat menggantikan if-else sederhana:

```javascript
// Menggunakan if-else
let result;
if (age >= 18) {
    result = "Dewasa";
} else {
    result = "Anak-anak";
}

// Menggunakan ternary operator
let result = age >= 18 ? "Dewasa" : "Anak-anak";
```

Ternary operator lebih ringkas, tetapi kurang cocok untuk kondisi yang kompleks atau memerlukan banyak baris kode.

## Nested Ternary
Kita dapat menumpuk ternary operator, tetapi ini bisa membuat kode sulit dibaca:

```javascript
let category = age < 13 ? "Anak" : age < 20 ? "Remaja" : "Dewasa";
```

Sebaiknya hindari nested ternary yang terlalu dalam untuk menjaga keterbacaan kode.

## Kapan Menggunakan
- Untuk assignment sederhana berdasarkan kondisi.
- Dalam return statement fungsi.
- Untuk membuat kode lebih ringkas.

Ingat, gunakan ternary operator dengan bijak agar kode tetap mudah dipahami!