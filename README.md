```vbnet
Me.TopMost = False
TextBox1.Focus()
System.Threading.Thread.Sleep(300)
Process.Start("C:\Program Files\Common Files\Microsoft Shared\ink\TabTip.exe")
System.Threading.Thread.Sleep(500)
Me.TopMost = True
```

```vbnet
C1FlexGrid1.ScrollPosition = New Point(0, C1FlexGrid1.ScrollPosition.Y)
```

```vbnet
' 固定列の右隣にスクロールを戻す（通常の意味での左端）
C1FlexGrid1.LeftCol = C1FlexGrid1.Cols.Frozen
```