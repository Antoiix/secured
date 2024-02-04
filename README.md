<h1>Secured</h1>

<h2 id="introduction">Introduction</h2>

<p>Welcome to the Secured repository! This project aims to provide a basic understanding of the
    concepts of hash functions and hash tables, commonly used in computer science for efficient data
    retrieval.</p>

<h2 id="hash-function">Hash Function</h2>

<p>A hash function is a mathematical function that takes an input (or 'message') and returns a fixed-size string of
    characters, which is typically a hash code. The primary purpose of a hash function is to map data of arbitrary
    size to a fixed-size value, making it easier to manage and retrieve data quickly.</p>

<p>Our hash function is :</p>
    
```c
int hash(char *key, int len)
{
    int hashed_key = len;

    for (int i = 0; key[i]; i++) {
        hashed_key += key[i];
        hashed_key += (hashed_key << 10);
        hashed_key ^= (hashed_key >> 6);
    }
    hashed_key += (hashed_key << 3);
    hashed_key ^= (hashed_key >> 11);
    hashed_key += (hashed_key << 15);
    return my_abs(hashed_key);
}
```

<p>Common properties of a good hash function include:</p>
<ul>
    <li><strong>Deterministic</strong>: For the same input, the hash function should always produce the same
        output.</li>
    <li><strong>Efficient</strong>: The computation of the hash should be fast.</li>
    <li><strong>Uniform Distribution</strong>: Ideally, the hash values should be uniformly distributed to avoid
        collisions.</li>
</ul>

<h2 id="hash-table">Hash Table</h2>

<p>A hash table, or hash map, is a data structure that implements an associative array abstract data type. It uses a
    hash function to map keys to corresponding values, allowing for efficient data retrieval. The hash function
    determines the index or 'bucket' where the key-value pair will be stored.</p>

<h3>Components of a Hash Table:</h3>

<ol>
    <li><strong>Hash Function</strong>: Maps keys to indices in the array.</li>
    <li><strong>Array or Buckets</strong>: Storage for key-value pairs.</li>
    <li><strong>Collision Resolution</strong>: Techniques to handle situations where two keys hash to the same
        index.</li>
</ol>

<p>Common collision resolution strategies include chaining (using linked lists in each bucket) and open addressing
    (finding the next available slot in the array).</p>

<h2 id="usage">Usage</h2>

<p>Create an hash table with the function ht_create and insert value with ht_insert. You can search a value with ht_search and delete with ht_delete. To free the hastable, use delete_hashtable function</p>
