# Create a range of numbered directories in Windows

1. Go to the destination folder.
2. Open command prompt.
3. Use command:
   ```
   for /l %i in (0,1,9) do md r0%i
   ```
   This will create _r00_-_r09_ folder range. `/L` stands for list of numbers. The numbers in parentheses are `(start, step, stop)`. Remember to put a space between `in` and `(`.