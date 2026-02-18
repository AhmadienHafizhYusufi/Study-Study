# Rangkuman Default Import/Export

## Pengantar
Default import/export adalah fitur ES6 yang memungkinkan kita mengekspor satu nilai utama dari modul dan mengimpornya dengan cara yang sederhana. Ini cocok untuk modul yang memiliki satu ekspor utama.

## Export Default
Untuk mengekspor nilai default:

```javascript
// user.js
const user = {
    name: 'John',
    age: 30
};

export default user;
```

Atau langsung pada deklarasi:

```javascript
export default function greet(name) {
    return `Hello, ${name}!`;
}

export default class User {
    constructor(name) {
        this.name = name;
    }
}
```

Setiap modul hanya boleh memiliki satu export default.

## Import Default
Untuk mengimpor nilai default:

```javascript
// main.js
import user from './user.js';
console.log(user.name); // John

import greet from './user.js'; // Jika export default adalah function
console.log(greet('Jane')); // Hello, Jane!
```

Kita dapat menggunakan nama apa saja saat import, karena itu adalah default:

```javascript
import myUser from './user.js';
import hello from './user.js'; // Jika function
```

## Kombinasi dengan Named Export
Modul dapat memiliki export default dan named exports sekaligus:

```javascript
// utils.js
export default function mainFunction() {
    // ...
}

export const helper = 'helper';
export function secondary() {
    // ...
}
```

Import:

```javascript
import mainFunc, { helper, secondary } from './utils.js';
```

## Keuntungan
- Sederhana untuk modul dengan satu ekspor utama.
- Nama import dapat fleksibel.
- Cocok untuk library atau komponen utama.

Default import/export memberikan fleksibilitas dalam struktur modul JavaScript!