# calucatest

```vbnet 

Public Class MainForm
    Public Sub New()
        InitializeComponent()
        Me.DoubleBuffered = True ' 再描画の安定
    End Sub

    Private Sub MainForm_Shown(sender As Object, e As EventArgs) Handles Me.Shown
        With Button1
            .FlatStyle = FlatStyle.Flat
            .UseVisualStyleBackColor = False
            .BackColor = Color.LightBlue
            .FlatAppearance.BorderSize = 0
            .FlatAppearance.MouseOverBackColor = Color.LightBlue
            .FlatAppearance.MouseDownBackColor = Color.LightBlue
        End With
    End Sub
End Class

```


```vbnet
' TabTip.exe を起動（起動していなければ）
If Process.GetProcessesByName("TabTip").Length = 0 Then
    Process.Start("C:\Program Files\Common Files\Microsoft Shared\ink\TabTip.exe")
End If
```

```vbnet
Public Class Form1
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        ' フルスクリーン表示（枠なし）
        Me.FormBorderStyle = FormBorderStyle.None
        Me.WindowState = FormWindowState.Maximized
        Me.TopMost = True ' 他のウィンドウの上に表示（任意）

        ' タスクバーを非表示にする
        HideTaskbar()
    End Sub

    Private Sub Form1_FormClosing(sender As Object, e As FormClosingEventArgs) Handles MyBase.FormClosing
        ' タスクバーを戻す
        ShowTaskbar()
    End Sub

    ' タスクバーを隠す
    Private Sub HideTaskbar()
        Dim taskBarHandle As IntPtr = FindWindow("Shell_TrayWnd", Nothing)
        ShowWindow(taskBarHandle, SW_HIDE)
    End Sub

    ' タスクバーを表示する
    Private Sub ShowTaskbar()
        Dim taskBarHandle As IntPtr = FindWindow("Shell_TrayWnd", Nothing)
        ShowWindow(taskBarHandle, SW_SHOW)
    End Sub

    ' Win32 API 宣言
    Private Declare Function FindWindow Lib "user32.dll" Alias "FindWindowA" (
        ByVal lpClassName As String, ByVal lpWindowName As String) As IntPtr

    Private Declare Function ShowWindow Lib "user32.dll" (
        ByVal hWnd As IntPtr, ByVal nCmdShow As Integer) As Boolean

    Private Const SW_HIDE As Integer = 0
    Private Const SW_SHOW As Integer = 5
End Class
```
