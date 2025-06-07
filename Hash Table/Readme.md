# Hash Table

A **hash table** (or hash map) is a **data structure** that stores data in
**key-value pairs**, and allows for **fast lookup**, **insertion**, and
**deletion** — often in **O(1)** time.

It’s like a real-life dictionary:

- You look up a word (**key**),
- You find its meaning (**value**).

## How Does It Work?

1. Key is passed to a hash function.
2. Hash function converts key into an index (a number).
3. The value is stored at that index in an array.

![Hash Function and Table](./images/1.webp)

## Hash Tables in Programming Languages

### C++

In C++, a hash table is implemented using unordered_map (from <unordered_map>).
It stores key-value pairs, and allows constant-time (average) lookup, insertion,
and deletion.
