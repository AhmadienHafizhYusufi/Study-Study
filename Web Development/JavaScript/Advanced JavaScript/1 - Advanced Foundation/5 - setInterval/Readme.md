# Rangkuman setInterval

## Pengantar
`setInterval` adalah fungsi global dalam JavaScript yang digunakan untuk menjalankan sebuah fungsi atau mengeksekusi kode secara berulang dengan interval waktu tertentu. Ini sangat berguna untuk tugas-tugas yang perlu dilakukan secara periodik, seperti update UI atau polling data.

## Sintaks
Sintaks dasar `setInterval` adalah:

```javascript
setInterval(function, interval, arg1, arg2, ...)
```

- `function`: Fungsi yang akan dieksekusi berulang kali.
- `interval`: Interval waktu dalam milidetik (ms) antara setiap eksekusi.
- `arg1, arg2, ...`: Argumen opsional yang akan diteruskan ke fungsi.

Fungsi ini mengembalikan ID interval yang dapat digunakan untuk menghentikan eksekusi.

## Contoh Penggunaan
Contoh sederhana untuk membuat timer:

```javascript
let counter = 0;

const intervalId = setInterval(() => {
    counter++;
    console.log(`Counter: ${counter}`);
    
    if (counter >= 5) {
        clearInterval(intervalId);
        console.log("Interval dihentikan");
    }
}, 1000);

// Output: Counter: 1, Counter: 2, ..., Counter: 5, Interval dihentikan
```

Dengan argumen:

```javascript
function updateTime(name) {
    console.log(`${name}: ${new Date().toLocaleTimeString()}`);
}

setInterval(updateTime, 2000, "Waktu saat ini");
// Output setiap 2 detik: Waktu saat ini: 10:30:45
```

## Membatalkan Interval
Gunakan `clearInterval` untuk menghentikan eksekusi berulang:

```javascript
const intervalId = setInterval(() => {
    console.log("Ini akan berhenti");
}, 1000);

// Menghentikan setelah 5 detik
setTimeout(() => {
    clearInterval(intervalId);
    console.log("Interval dihentikan");
}, 5000);
```

## Perbedaan dengan setTimeout
- `setTimeout`: Menjalankan fungsi sekali setelah delay.
- `setInterval`: Menjalankan fungsi berulang kali setiap interval.

## Kasus Penggunaan
- Update tampilan real-time (jam, counter).
- Polling data dari server.
- Animasi atau efek visual berulang.
- Monitoring atau logging periodik.

## Perhatian
- Interval tidak selalu tepat karena JavaScript single-threaded; jika fungsi memakan waktu lama, eksekusi berikutnya mungkin tertunda.
- Gunakan `clearInterval` untuk menghindari memory leaks.
- Untuk interval yang lebih akurat, pertimbangkan `requestAnimationFrame` untuk animasi.

`setInterval` adalah alat yang powerful untuk tugas-tugas periodik, tetapi gunakan dengan bijak untuk menghindari masalah performa!