haskell-container-types
=====

# Data.Vector

``` haskell
import Data.Vector (Vector)
import qualified Data.Vector as Vector
```

The `Vector a` type.

**Advantages**

* O(1) indexing.
* O(1) slicing.
* O(n) concatenation, but in practice is fast. With unboxed version,
  should happen in cache.
* Fast traversal, usually in cache.
* Supports unboxed, packed data structure.
* Supports fusion on some operations.
* Immutable and mutable flavours.
* O(1) update in mutable form.

**Disadvantages**

* O(n) insertion for pure version.

**When to use:** You need to store a set of elements,
  want index lookup and don't care about duplicates.

**When not to use:** You want unique elements or non-integer based
  indexing or fast insertion on a pure data structure.

# Data.List

``` haskell
import qualified Data.List as List
```

The `[a]` type.

**Advantages**

* O(1) front-insertion (consing).

**Disadvantages**

* O(n) size calculation.
* O(n) indexing.
* O(n) slicing.
* Traversal requires mainline memory pointer arithmetic; not in cache.

**When to use:** To use for looping constructs.

**When not to use:** You want fast traversal, indexing, slicing or
  basically anything performant.


# Data.Set

``` haskell
import Data.Set (Set)
import qualified Data.Set as Set
```

The `Set a` type.

**Advantages**

* O(1) size check.
* Explicit that every element is unique.
* O(log n) member check.
* O(log n) insert and delete.
* O(n+m) appending and intersection.

**When to use:** You need to store a set of unique elements and want
  fast existence check.

**When not to use:** You want fast existence check or fast insertion
  or appending.

# Data.IntSet

``` haskell
import Data.IntSet (IntSet)
import qualified Data.IntSet as IntSet
```

The `IntSet` type.

**Advantages**

* O(min(n,W)) membership test.
* O(min(n,W)) insert/delete.

**When to use:** You have the same requirements as `Set a`, but want
  it to be faster on `Int`.

**When not to use:** You still want faster existence check or fast
  insertion or appending.


# Data.Map

``` haskell
import Data.Map (Map)
import qualified Data.Map as Map
```

The `Map k a` type.

**Advantages**

* O(1) size calculation.
* Explicit about key/value relationship.
* O(log n) lookup/membership test.
* O(log n) insertion/deletion/modification.
* O(n+m) set operations (union/diff/intersect).

**When to use:** When you have a mapping from unique keys to unique
  values and want to be explicit about it.

**When not to use:** When you have integer keys, you can use something
  more specific to the key type.

# Data.Sequence

``` haskell
import Data.Sequence (Seq)
import qualified Data.Sequence as Seq
```

The `Seq a` type.

**Advantages**

* O(1) appending/consing.
* O(log(min(n1,n2))) concatenation.
* O(1) size calculation.
* O(log(min(i,n-i))) indexing.
* O(log(min(i,n-i))) slicing.

**When to use:** When you want fast appending/concatenation and decent
  indexing.

## Data.Array


``` haskell
import
import
```

…

**Advantages**

…

**Disadvantages**

…

**When to use:** …

# Data.HashSet

``` haskell
import Data.HashSet (HashSet)
import qualified Data.HashSet as HashSet
```

The `HashSet a` type.

**Advantages**

* O(min(n,W)) member test
* O(min(n,W)) insert/delete
*

**Disadvantages**

* O(n) size calculation.
* O(n+m) union/difference/intersect

**When to use:** When you have a hashable data type and want the
  benefits of `Set a` but with better performance.

## Data.HashTable

``` haskell
import
import
```

…

**Advantages**

…

**Disadvantages**

…

**When to use:** Fastest possible inserts and fast lookups.

## Data.Queue

``` haskell
import
import
```

…

**Advantages**

…

**Disadvantages**

…

## Data.Matrix

``` haskell
import
import
```

…

**Advantages**

…

**Disadvantages**

…
