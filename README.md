# The ahk shell menu

Displays a popup menu when you extended-right-click in file explorer.   
I use this to hold scripts targeting selected files and/or folders.  
Creates a menu for ahk/exe files and runs them on click, so they can be v1 or v2 or exe.  
It also autoloads scripts in the respective folder.

**One way for the ahk scripts loop the selected files is**  


```ahk
GoSub, Main

Main() {
clip := ClipToVar()
Loop, parse, clip, `n, `r
{
  targetFile := A_LoopField
  ;YOUR CODE HERE
}

;function: copy selection to clipboard to var
ClipToVar() {
  cliptemp := clipboardall ;backup
  clipboard = 
  send ^c
  clipwait, 1
  clip := clipboard
  clipboard := cliptemp    ;restore
  return clip
}
```
