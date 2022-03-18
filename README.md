# .net
***************************************************************************<br>
Using Window Form Application to Perform Reversal,padding and Triming Operations <br>
****************************************************************************<br>
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
output:<br>
![Screenshot (16)](https://user-images.githubusercontent.com/99865138/158741646-2208d77c-1fd1-4de3-82b8-f1487a95dbd6.png)<br>
![Screenshot (21)](https://user-images.githubusercontent.com/99865138/158744755-6607105d-0a85-4a1b-a8fa-6347a3c2a37d.png)<br>
![Screenshot (22)](https://user-images.githubusercontent.com/99865138/158744842-7ab98538-81a0-4bef-9fcb-40114f09dfb5.png)<br>
![Screenshot (23)](https://user-images.githubusercontent.com/99865138/158744979-35a6b43f-aaaa-4b0c-b30e-d3cd8314cb6f.png)<br>

********************************************************************************************<br>
c# program to Create the Progress Bar<br>
**********************************************************************************************<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading;<br>
using System.Windows.Forms;<br>
<br>
namespace WindowsFormsApp3<br>
{<br>
 public partial class Form1 : Form<br>
{<br>
public Form1()<br>
{<br>
InitializeComponent();<br>
}<br>
private void Form1_Load(object sender, EventArgs e)<br>
{<br>
backgroundWorker1.WorkerReportsProgress = true;<br>
backgroundWorker1.RunWorkerAsync();<br>

 }<br>

 private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)<br>
 {<br>
   for (int i = 1; i <= 100; i++)<br>
  {<br>
  Thread.Sleep(50);<br>
 backgroundWorker1.ReportProgress(i);<br>
 }<br>
 private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)<br>
 {<br>
 progressBar1.Value = e.ProgressPercentage;<br>
 this.Text = "Progress: " + e.ProgressPercentage.ToString() + "%";<br>
  }<br>
  }<br>

}<br>
Output:<br>
![Screenshot (27)](https://user-images.githubusercontent.com/99865138/158747221-29708268-367f-4989-9245-6f3ebeaf2e1d.png)<br>
![Screenshot (28)](https://user-images.githubusercontent.com/99865138/158747303-55641805-7391-45d2-b9a6-dbd7da1fce6d.png)<br>

******************************************************************************************<br>
Develop a Window form Application to Create Flat Clock<br>
*********************************************************************************************<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace WindowsFormsApp5<br>
{<br>
public partial class Form1 : Form<br>{<br>
public Form1()<br>
{<br>
 InitializeComponent();<br>
 }<br>
  private void Form1_Load(object sender, EventArgs e)<br>
  {<br>
  System.Timers.Timer timer = new System.Timers.Timer();<br>
  timer.Interval = 1000;//1s 	<br>
  timer.Elapsed += Timer_Elapsed;<br>
  timer.Start();<br>
  }<br>
 private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e)<br>
{<br>
circularProgressBar1.Invoke((MethodInvoker)delegate<br>
 {<br>
 circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss"); circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM  }); <br>
 });<br>
 }<br>
 }<br>

}<br>
Output:<br>
![Screenshot (30)](https://user-images.githubusercontent.com/99865138/158941709-6c939bc5-045b-4adb-8116-664e6b8185bd.png)<br>
***********************************************************************************************<br>
C# program a Number Guessing game
