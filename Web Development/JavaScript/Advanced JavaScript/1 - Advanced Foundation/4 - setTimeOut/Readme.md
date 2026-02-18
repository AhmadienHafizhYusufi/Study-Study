# Rangkuman setTimeout

## Pengantar
`setTimeout` adalah fungsi global dalam JavaScript yang digunakan untuk menjalankan sebuah fungsi atau mengeksekusi kode setelah jangka waktu tertentu (delay). Ini adalah bagian dari Web APIs dan sangat berguna untuk menunda eksekusi kode tanpa memblokir thread utama.

## Sintaks
Sintaks dasar `setTimeout` adalah:

```javascript
setTimeout(function, delay, arg1, arg2, ...)
```

- `function`: Fungsi yang akan dieksekusi setelah delay.
- `delay`: Waktu tunggu dalam milidetik (ms).
- `arg1, arg2, ...`: Argumen opsional yang akan diteruskan ke fungsi.

Fungsi ini mengembalikan ID timeout yang dapat digunakan untuk membatalkan eksekusi.

## Contoh Penggunaan
Contoh sederhana:

```javascript
console.log("Mulai");

setTimeout(() => {
    console.log("Ini akan muncul setelah 2 detik");
}, 2000);

console.log("Selesai");
// Output: Mulai, Selesai, lalu setelah 2 detik: Ini akan muncul setelah 2 detik
```

Dengan argumen:

```javascript
function greet(name) {
    console.log(`Halo, ${name}!`);
}

setTimeout(greet, 1000, "John");
// Output setelah 1 detik: Halo, John!
```

## Membatalkan Timeout
Gunakan `clearTimeout` untuk membatalkan timeout sebelum dieksekusi:

```javascript
const timeoutId = setTimeout(() => {
    console.log("Ini tidak akan muncul");
}, 5000);

// Membatalkan
clearTimeout(timeoutId);
```

## Perbedaan dengan setInterval
- `setTimeout`: Menjalankan fungsi sekali setelah delay.
- `setInterval`: Menjalankan fungsi berulang kali setiap interval waktu.

## Kasus Penggunaan
- Menunda eksekusi kode (misalnya, animasi atau notifikasi).
- Membuat delay dalam operasi asynchronous.
- Mengimplementasikan polling atau retry mechanism.
- Dalam event handling untuk debounce.

`setTimeout` sangat penting dalam pemrograman asynchronous JavaScript dan membantu membuat aplikasi yang lebih responsif!