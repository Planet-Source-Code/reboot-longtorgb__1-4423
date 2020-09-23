<div align="center">

## LongToRGB


</div>

### Description

Converts Long values (used by getpixel and other low level color functions) into RGB values that you can use. Useful if you want to manually remap an image or make some kind of color effect.
 
### More Info
 
Long color value (from getpixel or rgb(), etc)

Three paramaters, r g and b, red green blue


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Reboot](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/reboot.md)
**Level**          |Unknown
**User Rating**    |5.0 (25 globes from 5 users)
**Compatibility**  |VB 3\.0, VB 4\.0 \(16\-bit\), VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__1-1.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/reboot-longtorgb__1-4423/archive/master.zip)





### Source Code

```
Private Type zRGB
R As Long
G As Long
B As Long
End Type
Private Sub Form_Load()
'this is just an example
'if you don't tweak the code, you will have to
'dim a variable as "zRGB" that stores the returns
Dim cRGB As zRGB
cRGB = LongToRGB(RGB(255, 250, 255))
MsgBox cRGB.R & ", " & cRGB.G & ", " & cRGB.B
End
End Sub
Private Function LongToRGB(ColorValue As Long) As zRGB
Dim rCol As Long, gCol As Long, bCol As Long
rCol = ColorValue And &H10000FF 'this uses binary comparason
gCol = (ColorValue And &H100FF00) / (2 ^ 8)
bCol = (ColorValue And &H1FF0000) / (2 ^ 16)
LongToRGB.R = rCol
LongToRGB.G = gCol
LongToRGB.B = bCol
End Function
```

