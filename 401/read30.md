>> Hash Tables

> Basically hash-table is a key-value pair dictionary. What makes it different with the regular dictionary is the “hashing” process. Before a key is inside a bucket/slot, “hashing” needs to be performed to find an index of buckets, as this specific bucket will hold the key-value pair in the future.This is one of the reason why hash-table has a strong average case performance.
 The main advantage of hash tables over other data structures is speed . The access time of an element is on average O(1), therefore lookup could be performed very fast. Hash tables are particularly efficient when the maximum number of entries can be predicted in advance.

-   **Quick summary**: unordered collection that maps keys to values using hashing.
-   **Also known as**: hash, hash map, map, unordered map, dictionary, associative array.
-   **Important facts**:
    -   Stores data as key-value pairs.
    -   Can be seen as an evolution of arrays that removes the limitation of sequential numerical indices and allows using flexible keys instead.
    -   For any given non-numeric key, _hashing_ helps get a numeric index to look up in the underlying array.
    -   If hashing two or more keys returns the same value, this is called a _hash collision_. To mitigate this, instead of storing actual values, the underlying array may hold references to linked lists that, in turn, contain all values with the same hash.
    -   A _set_ is a variation of a hash table that stores keys but not values.
-   **Pros**:
    -   Keys can be of many data types. The only requirement is that these data types are hashable.
    -   Average search, insertion and deletion are `O(1)`.
-   **Cons**:
    -   Worst-case lookups are `O(n)`.
    -   No ordering means looking up minimum and maximum values is expensive.
    -   Looking up the value for a given key can be done in constant time, but looking up the keys for a given value is `O(n)`.
-   **Notable uses**:
    -   Caching.
    -   Database partitioning.
-   **Time complexity** (worst case):
    -   Access: `O(n)`
    -   Search: `O(n)`
    -   Insertion: `O(n)`
    -   Deletion: `O(n)`
