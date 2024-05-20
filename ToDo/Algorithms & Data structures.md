this is my journey in re-learning of algorithms and data structures and here what I'm going to do:
1. binary search:
   1. binary search is O(log n) because we always jump to the middle of the array and cut the array into half
   2. we calculate the mid point by the this formula Floor (low + (high -low) / 2)
   3. low is inclusive and high is exclusive  = \[low, high) 
   
C# implementation: 
   
```csharp
public static bool Search(int[] heyStack, int needle)
        {
            var low = 0;
            var high = heyStack.Length;

            do
            {
                var mid = low + (high - low) / 2;
                var value = heyStack[mid];
                if (value == needle)
                {
                    return true;
                }
                else if (needle < value)
                {
                    high = mid;
                }
                else if (needle > value)
                {
                    low = mid + 1;
                }



            } while (low < high);

            return false;
        }
```

   Rust implementation:
```rust
fn binary_search(hey_stack: &Vec<i32>, needle: i32) -> bool {
    let mut low: usize = 0;
    let mut high: usize = hey_stack.len();
    while low < high {
        let mid = low + (high - low) / 2;
        let value = hey_stack[mid];
        
        if value == needle {
            return true;
        }
        if needle < value {
            high = mid;
        } else if needle > value {
            low = mid + 1;
        }
    }
    false
}
```

2. bubble sort:
   in bubble sort we do an N time of iteration and compare an item with it's neighbor if it's larger then it's neighbor we swap between them with the first iteration we end up  with largest element to be at the end of the array so in the second iteration we do the same thing and exclude the last position and keep doing this utile all the array is sorted.
   time complexity is O(N^2)
   C# implementation
   ```csharp
public static void Sort(int[] arr)
{
    for (int i = 0; i < arr.Length - 2; i++)
    {
        for (int k = 0; k < arr.Length - 1 - i; k++)
        {
            if (arr[k] > arr[k + 1])
            {
                var temp = arr[k];
                arr[k] = arr[k + 1];
                arr[k + 1] = temp;
            }

        }
    }
}
```

Rust implementation:

```rust 
pub fn bubble_sort(arr: &mut Vec<i32>) {
    let mut i = 0;
    let mut k = 0;
    
    while i < arr.len() - 2 {
        while k < arr.len() - 1 - i {
            if arr[k] > arr[k + 1] {
                let temp = arr[k];
                arr[k] = arr[k + 1];
                arr[k + 1] = temp
            }
            k = k + 1;
        }
        k = 0;
        i = i + 1;
    }
}
```

1. linked list: 
   implement complete linked-lined with all it's operation in C# and rust if possible
4. Stack:
   implement Stack in C# and JS 
   // TODO: write here what have you learn and code snippet  of the implementation
5. Quick sort:
   Implement Quick sort in C# and rust
   // TODO: write here what have you learn and code snippet  of the implementation

### To be continued !
