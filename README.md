Dim input As String = "6×6＝36" ' 「×」は U+00D7 など
input = input.Replace("×", "*") ' U+00D7
input = input.Replace("✖︎", "*") ' U+2716 + variation
input = input.Replace("✕", "*") ' U+2715