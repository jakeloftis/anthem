# anthem
#include <Vis2>  ; Equivalent to #include .\lib\Vis2.ahk

Loop, 84
{

;Scan guns on the selected row

;Read gun name and copy to clipboard
OCR([2906, 595, 422, 41]).clipboard()

;Switch focus to Google Sheets
WinActivate, Script Dump - Google Sheets - Google Chrome, 

;Paste clipboard with gun name in column A
Send, ^v

Sleep, 500

;Move right to columb B to prepare for inscriptions
Send, {right}

;Read left half of inscriptions
OCR([3075, 839, 286, 120]).clipboard()

;Paste clipboard with left half of inscriptions
Send, ^v
Sleep, 500

;Move right to column C to make room for right half of inscriptions
Send, {right}

;Read right half of inscriptions
OCR([3376, 839, 286, 120]).clipboard()

Sleep, 500

;Paste clipboard with right half of inscriptions
Send, ^v

Sleep, 500

;Move down ten rows and left two columns to column A to prepare for next gun name paste
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {left}
Sleep,50
Send, {left}
Sleep,50

;Switch focus to Xbox One app
WinActivate, Xbox
Sleep, 500

;Go right to the next gun in inventory
Send, {right down}
Sleep, 50
Send, {right up}
Sleep, 500

;Read gun name and copy to clipboard
OCR([2906, 595, 422, 41]).clipboard()

;Switch focus to Google Sheets
WinActivate, Script Dump - Google Sheets - Google Chrome, 

;Paste clipboard with gun name in column A
Send, ^v

Sleep, 500

;Move right to columb B to prepare for inscriptions
Send, {right}

;Read left half of inscriptions
OCR([3075, 839, 286, 120]).clipboard()

;Paste clipboard with left half of inscriptions
Send, ^v
Sleep, 500

;Move right to column C to make room for right half of inscriptions
Send, {right}

;Read right half of inscriptions
OCR([3376, 839, 286, 120]).clipboard()

Sleep, 500

;Paste clipboard with right half of inscriptions
Send, ^v

Sleep, 500

;Move down ten rows and left two columns to column A to prepare for next gun name paste
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {left}
Sleep,50
Send, {left}
Sleep,50

;Switch focus to Xbox One app
WinActivate, Xbox
Sleep, 500

;Go right to the next gun in inventory
Send, {right down}
Sleep, 50
Send, {right up}
Sleep, 500

;Read gun name and copy to clipboard
OCR([2906, 595, 422, 41]).clipboard()

;Switch focus to Google Sheets
WinActivate, Script Dump - Google Sheets - Google Chrome, 

;Paste clipboard with gun name in column A
Send, ^v

Sleep, 500

;Move right to columb B to prepare for inscriptions
Send, {right}

;Read left half of inscriptions
OCR([3075, 839, 286, 120]).clipboard()

;Paste clipboard with left half of inscriptions
Send, ^v
Sleep, 500

;Move right to column C to make room for right half of inscriptions
Send, {right}

;Read right half of inscriptions
OCR([3376, 839, 286, 120]).clipboard()

Sleep, 500

;Paste clipboard with right half of inscriptions
Send, ^v

Sleep, 500

;Move down ten rows and left two columns to column A to prepare for next gun name paste
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {down}
Sleep,50
Send, {left}
Sleep,50
Send, {left}
Sleep,50

;Switch focus to Xbox One app
WinActivate, Xbox
Sleep, 500

;Go right to the next gun in inventory
Send, {right down}
Sleep, 50
Send, {right up}
Sleep, 500

;Move down to the next row
Send, {left down}
Sleep, 50
Send, {left up}
Sleep, 50
Send, {left down}
Sleep, 50
Send, {left up}
Sleep, 50
Send, {down down}
Sleep, 50
Send, {down up}
Sleep, 500

}

ESC::exitapp


===================

Option1:

Extract inscription stats from columb B - Invalid data entries will be marked with #VALUE

=MID(B1,IFERROR(FIND("+",B1),FIND("-",B1)),LEN(B1))

==

Option 2:

Extract inscription stats from columb B - Invalid data entries will be blank cells

=REPLACE(B1,1,MIN(FIND("-",B1&"-"),FIND("+",B1&"+"))-1,"")

==

Combine columns B and C to list all 4 inscriptions

=FILTER({B1:B10;C1:C10}, LEN({B1:B10;C1:C10))

Will need updated once loop script is changed from 10 {down} to 5 {down}

=FILTER({B1:B5;C1:C5}, LEN({B1:B5;C1:C5))

===================
