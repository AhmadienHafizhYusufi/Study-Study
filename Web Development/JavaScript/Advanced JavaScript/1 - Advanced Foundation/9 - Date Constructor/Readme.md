# Rangkuman Date Constructor

## Pengantar
`Date` adalah constructor bawaan JavaScript yang digunakan untuk bekerja dengan tanggal dan waktu. Objek `Date` merepresentasikan titik waktu tertentu dan menyediakan berbagai method untuk memanipulasi dan memformat tanggal/waktu.

## Cara Membuat Objek Date
Ada beberapa cara untuk membuat objek Date:

### 1. Tanpa Parameter (Tanggal/Waktu Saat Ini)
```javascript
const now = new Date();
console.log(now); // Output: Wed Feb 18 2026 10:30:00 GMT+0700 (WIB)
```

### 2. Dengan String Tanggal
```javascript
const date1 = new Date('2026-02-18');
const date2 = new Date('February 18, 2026 10:30:00');
```

### 3. Dengan Parameter Numerik
```javascript
// new Date(year, month, day, hours, minutes, seconds, milliseconds)
// Catatan: month dimulai dari 0 (Januari = 0)
const date = new Date(2026, 1, 18, 10, 30, 0, 0); // 18 Feb 2026 10:30:00
```

### 4. Dengan Timestamp
```javascript
const timestamp = 1708239000000; // Milidetik sejak 1 Jan 1970
const date = new Date(timestamp);
```

## Method Umum
### Getter Methods
```javascript
const date = new Date();

date.getFullYear();    // Tahun (2026)
date.getMonth();       // Bulan (0-11, 1 = Feb)
date.getDate();        // Tanggal (1-31)
date.getDay();         // Hari (0-6, 0 = Minggu)
date.getHours();       // Jam (0-23)
date.getMinutes();     // Menit (0-59)
date.getSeconds();     // Detik (0-59)
date.getMilliseconds(); // Milidetik (0-999)
date.getTime();        // Timestamp
```

### Setter Methods
```javascript
date.setFullYear(2027);
date.setMonth(5);      // Juni
date.setDate(15);
date.setHours(14);
date.setMinutes(45);
```

### Method Format
```javascript
date.toDateString();   // "Wed Feb 18 2026"
date.toTimeString();   // "10:30:00 GMT+0700 (WIB)"
date.toLocaleDateString(); // Format lokal tanggal
date.toLocaleTimeString(); // Format lokal waktu
date.toISOString();    // "2026-02-18T03:30:00.000Z"
```

## Operasi dengan Date
### Menghitung Selisih
```javascript
const date1 = new Date('2026-02-18');
const date2 = new Date('2026-02-20');
const diffTime = Math.abs(date2 - date1);
const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
console.log(diffDays); // 2
```

### Menambah/Mengurangi Tanggal
```javascript
const date = new Date();
date.setDate(date.getDate() + 7); // Tambah 7 hari
```

## Perhatian
- Bulan dimulai dari 0 (0 = Januari, 11 = Desember).
- Date objects mutable, operasi akan mengubah objek asli.
- Untuk parsing string tanggal, gunakan format ISO 8601 untuk konsistensi.
- Timezone tergantung pada environment (browser/Node.js).

Date constructor sangat penting untuk menangani tanggal dan waktu dalam aplikasi JavaScript!