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
