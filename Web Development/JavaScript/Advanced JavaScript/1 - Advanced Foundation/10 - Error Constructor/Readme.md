# Rangkuman Error Constructor

## Pengantar
`Error` adalah constructor bawaan JavaScript yang digunakan untuk membuat objek error. Objek error digunakan untuk menangkap dan menangani kesalahan (exceptions) dalam kode. JavaScript memiliki beberapa tipe error bawaan yang mewarisi dari `Error`.

## Cara Membuat Objek Error
### 1. Menggunakan Constructor Error
```javascript
const error = new Error('Terjadi kesalahan!');
console.log(error.message); // "Terjadi kesalahan!"
```

### 2. Melempar Error
```javascript
throw new Error('Ini adalah error yang dilempar');
```

## Tipe Error Bawaan
JavaScript memiliki beberapa subclass Error:

- **`Error`**: Error umum
- **`TypeError`**: Ketika nilai bukan tipe yang diharapkan
- **`ReferenceError`**: Ketika mereferensikan variabel yang tidak ada
- **`SyntaxError`**: Ketika ada kesalahan sintaks
- **`RangeError`**: Ketika nilai di luar range yang valid
- **`URIError`**: Ketika `encodeURI()` atau `decodeURI()` digunakan dengan URI yang tidak valid
- **`EvalError`**: Ketika terjadi error di dalam `eval()`

```javascript
const typeError = new TypeError('Tipe data salah');
const refError = new ReferenceError('Variabel tidak ditemukan');
```

## Properties Objek Error
Setiap objek Error memiliki properties:

- **`message`**: Pesan error
- **`name`**: Nama tipe error
- **`stack`**: Stack trace (urutan pemanggilan fungsi)

```javascript
try {
    throw new Error('Test error');
} catch (error) {
    console.log(error.name);    // "Error"
    console.log(error.message); // "Test error"
    console.log(error.stack);   // Stack trace lengkap
}
```

## Menggunakan Try-Catch
Try-catch digunakan untuk menangkap dan menangani error:

```javascript
try {
    // Kode yang mungkin menyebabkan error
    const result = riskyFunction();
    console.log(result);
} catch (error) {
    // Menangani error
    console.error('Error terjadi:', error.message);
} finally {
    // Kode yang selalu dieksekusi
    console.log('Cleanup dilakukan');
}
```

## Membuat Custom Error
Kita dapat membuat subclass Error sendiri:

```javascript
class ValidationError extends Error {
    constructor(message) {
        super(message);
        this.name = 'ValidationError';
    }
}

throw new ValidationError('Data tidak valid');
```

## Best Practices
- Selalu gunakan tipe error yang sesuai (TypeError untuk type issues, dll.)
- Berikan pesan error yang jelas dan deskriptif
- Gunakan try-catch untuk operasi yang berpotensi gagal
- Jangan gunakan error untuk control flow normal
- Log stack trace untuk debugging

Error constructor sangat penting untuk debugging dan menulis kode JavaScript yang robust!