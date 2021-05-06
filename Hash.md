# Hash Tables

### What is a Hashtable?

- Hashtable is a data structure used to store information.
- Hash - A hash is the result of some algorithm taking an incoming string and converting it into a value that could be used for either security or some other purpose. In the case of a hashtable, it is used to determine the index of the array.
- Buckets - A bucket is what is contained in each index of the array of the hashtable. Each index is a bucket. An index could potentially contain multiple key/value pairs if a collision occurs.
- Collisions - A collision is what happens when more than one key gets hashed to the same location of the hashtable.

### Terminology

Hash: ability to encode the key that will eventually map to a specific location in the data structure that we can look at directly to retrieve the value
Buckets: what is contained in each index of teh array of the hashtable, each index is a bucket (index could contain multiple key-value pairs if a collision occurs)
Collisions: what happens when more than one key gets hashed to the same location of the hashtable

### Creating a Hash

Hashtable traditionally is created from an array
After you've created your array, do some sort of logic to turn that "key" into a numeric number value (example: Add or multiply all the ASCII values together, Multiply it by a prime number such as 599, Use modulo to get the remainder of the result, when divided by the total size of the array, Insert into the array at that index)
Each index of the array can hold many types of values
Each index of the array contain “buckets”, and each of these “buckets” holds one key/value pair combination
When there is no entry in a specific bucket, the buckets (each index of the array) all start null
The hash table starts each bucket empty and overwrites their value once a key generates a hash code that corresponds with an index

### Internal Methods

`Add()`
When adding a new key/value pair to a hashtable:
send the key to the GetHash method. Once you determine the index of where it should be placed, go to that index
Check if something exists at that index already, if it doesn’t, add it with the key/value pair. If something does exist, add the new key/value pair to the data structure within that bucket.

`Find()`
The Find takes in a key, gets the Hash, and goes to the index location specified. Once at the index location is found in the array, it is then the responsibility of the algorithm the iterate through the bucket and see if the key exists and return the value.

`Contains()`
The Contains method will accept a key, and return a bool on if that key exists inside the hashtable. The best way to do this is to have the contains call the GetHash and check the hashtable if the key exists in the table given the index returned.

`GetHash()`
The GetHash will accept a key as a string, conduct the hash, and then return the index of the array where the key/value should be placed.

### Double hashing

Double hashing is similar to linear probing and the only difference is the interval between successive probes. Here, the interval between probes is computed by using two hash functions.

Let us say that the hashed index for an entry record is an index that is computed by one hashing function and the slot at that index is already occupied. You must start traversing in a specific probing sequence to look for an unoccupied slot. The probing sequence will be:

index = (index + 1 _ indexH) % hashTableSize;
index = (index + 2 _ indexH) % hashTableSize;

and so on…

Here, indexH is the hash value that is computed by another hash function.

Implementation of hash table with double hashing
