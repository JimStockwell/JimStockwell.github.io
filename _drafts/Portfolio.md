- An image viewer for images served by the Library of Congress API.
  A demo in action is [here](https://master.d1etbrmn6sho17.amplifyapp.com) on AWS Amplify,
  and the source code is [here](https://github.com/JimStockwell/loc) in GitHub.
  Some features of interest:
  - It is written in React.
  - The "onLoad" event handler
    (in Detail's img element)
    calls event.persist()
    so that it can read synthetic event data.
    Otherwise, event.target ends up set to null and unusable.
  - Temporarily setting "borders: solid" was very helpful in getting the layout CSS acceptable.
  - The API data is read with JavaScript's standard "fetch".
  - When selected, the left hand navigation strip scrolls independently of the main image.
    That was done using the "overflow" CSS property in App and Nav,
    and a specified size for the container.
    (Without a specified size there is no concept of overflow).
- A multi-threaded merge sort done to explore C++'s `std::await` and `std::future` features.
  The source is [here](https://github.com/JimStockwell/multi-threaded-merge).
  Some features of interest:
  - `std::await` and `std::future` were very easy to introduce into the existing program.
    The only difficulties were:
    - A g++ extension I used could not be passed as-is through `async`.
      Specifically, variable-length arrays from C,
      described [here](https://en.cppreference.com/w/c/language/array),
      could not be passed through as-is.
      They had to be either allocated in the heap, or passed in the style `&a[0]` instead of `a`.
    - Some method was necessary to prevent an explosion of small threads.
      I chose a theshold array length, below which a direct call was made instead of an async call.
      This attempts to introduce some balance:
      only create a thread if there is some minimum work to justify it.
 
  
