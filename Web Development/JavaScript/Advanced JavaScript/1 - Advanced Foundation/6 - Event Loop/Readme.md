# Rangkuman Event Loop

## Pengantar
Event Loop adalah konsep fundamental dalam JavaScript yang menjelaskan bagaimana JavaScript menangani operasi asynchronous. Ini adalah mekanisme yang memungkinkan JavaScript menjalankan kode non-blocking meskipun JavaScript sendiri adalah single-threaded.

## Apa Itu Event Loop?
Event Loop adalah loop yang terus berjalan dan memeriksa apakah ada tugas yang perlu dieksekusi. Ia bertanggung jawab untuk mengelola eksekusi kode synchronous dan asynchronous, memastikan bahwa tugas-tugas asynchronous dieksekusi pada waktu yang tepat.

## Komponen Utama
Event Loop melibatkan beberapa komponen utama:

1. **Call Stack**: Tempat kode synchronous dieksekusi. Setiap fungsi yang dipanggil ditambahkan ke stack, dan dihapus ketika selesai.

2. **Web APIs**: Bagian dari browser (atau Node.js) yang menangani operasi asynchronous seperti `setTimeout`, `setInterval`, HTTP requests, dll.

3. **Callback Queue**: Antrian tempat callback dari operasi asynchronous menunggu untuk dieksekusi.

4. **Microtask Queue**: Antrian khusus untuk microtasks seperti Promise callbacks.

## Cara Kerja Event Loop
1. Kode mulai dieksekusi, fungsi ditambahkan ke Call Stack.
2. Ketika menemui operasi asynchronous (misalnya `setTimeout`), tugas tersebut dikirim ke Web APIs.
3. Ketika operasi asynchronous selesai, callback-nya ditambahkan ke Callback Queue.
4. Ketika Call Stack kosong, Event Loop memindahkan callback dari Callback Queue ke Call Stack untuk dieksekusi.
5. Proses ini berulang terus menerus.

## Contoh Sederhana
```javascript
console.log('Start');

setTimeout(() => {
    console.log('Timeout callback');
}, 0);

console.log('End');

// Output:
// Start
// End
// Timeout callback
```

Meskipun timeout 0ms, callback tetap dieksekusi setelah kode synchronous selesai.

## Microtasks vs Macrotasks
- **Macrotasks**: `setTimeout`, `setInterval`, I/O operations
- **Microtasks**: `Promise.then()`, `process.nextTick()` (Node.js)

Microtasks dieksekusi sebelum macrotasks, bahkan jika macrotask sudah siap.

```javascript
console.log('Start');

setTimeout(() => console.log('Timeout'), 0);

Promise.resolve().then(() => console.log('Promise'));

console.log('End');

// Output:
// Start
// End
// Promise
// Timeout
```

## Mengapa Penting?
Event Loop memungkinkan JavaScript menangani banyak tugas secara efisien tanpa memblokir UI. Ini krusial untuk aplikasi web yang responsif.

Memahami Event Loop membantu developer menulis kode asynchronous yang lebih baik dan menghindari masalah seperti callback hell atau race conditions.