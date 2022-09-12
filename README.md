# bmp-to-lcd
Converts bmp24 images to bmp1 and create byte array for 128x64 LCD screen. My LCD was МТ12864А, it contains 2 KS0108 LCD panel inside.
Main function contains 2 for cycles. First cycle convert bmp24 monochrome (or not) image to black and white 1bit image.
Second for cycle prepare suitable byte array for LCD.
To show image, LCD fill screen by each vertical byte from left to right. Just like this:
    0123456789............63
   +------------------------
0  |0  <-low                \
1  |0                       /
2  |0                       \
3  |0       LCD             /
4  |0     KS0108            \
5  |0                       /
6  |0                       \
7  |0 <- high               /
8  |0 <- low                \
.  |0                       /
.  |0                       \
.  |0                       /
63 |0 <-high                \
   +_______________________
    ^
  byte
