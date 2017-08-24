# Style text in the console

To style the message in the console use `%c` delimiters inside the message to split it to chunks. Then provide a style for every chunk.

 ```
 console.log(
    '%cRed apples %cand %cyellow bananas',
    'color: red',
    'color: black',
    'color: yellow'
 );
 ```

 Styles apply starting from `%c` until the end of the string. The ones defined later take precedence over the previous ones. In this example `color: black` overwrites `color: red` but is overwritten by `color: yellow`.