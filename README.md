# .net
using System;using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace windowApplication<br>
{<br>
 public partial class txtname : Form<br>
 {<br>
 public txtname()<br>
 {<br>
 InitializeComponent();<br>
 }<br>

 private void label2_Click(object sender, EventArgs e)<br>
 {<br>

 }<br>

 private void btnTrim_Click(object sender, EventArgs e)<b   
 {<br>
  string inputString;<br>
 inputString = txtInput.Text;<
 MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");<br>
   }<br>
private void btnRev_Click(object sender, EventArgs e)<br>
{<br>
 string inputString, revstr = "";<br>
  int Length;<br>
 inputString = txtInput.Text;<br>
 Length = inputString.Length - 1;<br>
 while (Length >= 0)<br>
 {<br>
 revstr = revstr + inputString[Length];<br>
 Length--;<br>
 }<br>
MessageBox.Show("Reverse String Is : " + revstr, "Result");<br>

 }<br>

  private void btnPad_Click_1(object sender, EventArgs e)<br>
  {<br>
   string inputString;<br>
  inputString = txtInput.Text;<br>
  inputString = inputString.PadLeft(10, '*');<br>
 inputString = inputString.PadRight(15, '*');<br>
 MessageBox.Show("String After Padding : " + inputString, "Result");<br>
 }<br>
 }<br>

}<br>
![Screenshot (16)](https://user-images.githubusercontent.com/99865138/158741646-2208d77c-1fd1-4de3-82b8-f1487a95dbd6.png)<br>

