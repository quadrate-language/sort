# sort

Sorting algorithms for arrays in Quadrate.

## Installation

```bash
quadpm install https://github.com/quadrate-language/sort
```

## Usage

```qd
use sort
use mem

fn main() {
    // Create array of integers
    5 8 * mem::alloc! -> arr
    5 arr 0 mem::set_i64
    2 arr 8 mem::set_i64
    8 arr 16 mem::set_i64
    1 arr 24 mem::set_i64
    9 arr 32 mem::set_i64

    // Sort ascending
    arr 5 sort::ints

    // Find min/max
    arr 5 sort::min -> minval
    arr 5 sort::max -> maxval

    // Binary search (array must be sorted)
    arr 5 8 sort::search -> idx

    // Check if sorted
    arr 5 sort::is_sorted -> sorted

    // Reverse array
    arr 5 sort::reverse

    arr mem::free
}
```

## API

### Functions

- `ints(arr:ptr count:i64 --)` - Sort i64 array ascending
- `ints_desc(arr:ptr count:i64 --)` - Sort i64 array descending
- `strings(arr:ptr count:i64 --)` - Sort string array ascending
- `strings_desc(arr:ptr count:i64 --)` - Sort string array descending
- `min(arr:ptr count:i64 -- minval:i64)` - Find minimum value
- `max(arr:ptr count:i64 -- maxval:i64)` - Find maximum value
- `is_sorted(arr:ptr count:i64 -- sorted:i64)` - Check if sorted
- `reverse(arr:ptr count:i64 --)` - Reverse array in place
- `search(arr:ptr count:i64 needle:i64 -- idx:i64)` - Binary search

## License

MIT
