# Rangkuman Named Import/Export

## Pengantar
Named import/export adalah fitur ES6 dalam JavaScript yang memungkinkan kita mengekspor dan mengimpor beberapa nilai dari modul dengan nama spesifik. Ini sangat berguna untuk berbagi fungsi, variabel, atau objek antar file.

## Export Named
Untuk mengekspor nilai dengan nama:

```javascript
// math.js
export const PI = 3.14159;

export function add(a, b) {
    return a + b;
}

export class Calculator {
    // ...
}
```

Atau menggunakan satu statement di akhir file:

```javascript
const PI = 3.14159;
function add(a, b) { return a + b; }
class Calculator {}

export { PI, add, Calculator };
```

## Import Named
Untuk mengimpor nilai yang diekspor:

```javascript
// main.js
import { PI, add, Calculator } from './math.js';

console.log(PI); // 3.14159
console.log(add(2, 3)); // 5
```

Kita dapat mengimpor sebagian saja:

```javascript
import { add } from './math.js';
```

Atau menggunakan alias:

```javascript
import { add as tambah, PI as phi } from './math.js';
console.log(tambah(2, 3)); // 5
console.log(phi); // 3.14159
```

## Import Semua
Menggunakan `*` untuk mengimpor semua named exports sebagai objek:

```javascript
import * as MathUtils from './math.js';
console.log(MathUtils.PI);
console.log(MathUtils.add(2, 3));
```

## Keuntungan
- Dapat mengekspor multiple values dari satu modul.
- Import hanya yang diperlukan, mengurangi bundle size.
- Nama yang eksplisit membuat kode lebih mudah dipahami.

Named import/export sangat penting dalam pengembangan aplikasi JavaScript modern untuk modularisasi kode!