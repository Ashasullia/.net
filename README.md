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
***************************************************************************************************<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace WindowsFormsApp10<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        static Random r = new Random();<br>
        int value;<br>
        int guessnum;<br>
        int win = 10;<br>
        int guess = 1;<br>
        TextBox textBox1;<br>
        RichTextBox richTextBox1;<br>
        RichTextBox richTextBox2;<br>
        Label label4;<br>
        public Form1()<br>
        {<br>
InitializeComponent();<br>

 value = r.Next(10);<br>
this.Controls.Clear();
this.BackColor = Color.SkyBlue;<br>
this.AutoSize = true;<br>
this.Padding = new Padding(16);<br>

Label label = new Label();<br>
 label.Text = "Pick a number between 1 and 100";<br>
 label.Bounds = new Rectangle(10, 20, 340, 40);<br>
 label.Font = new Font("Arial", 16);<br>
textBox1 = new TextBox();<br>
 textBox1.Bounds = new Rectangle(20, 50, 120, 80);<br>
 textBox1.Font = new Font("Arial", 24);<br>
  button1 = new Button();<br>
  button1.Text = " Check Your Guess ";<br>
  button1.Bounds = new Rectangle(160, 50, 120, 40);<br>
 button1.BackColor = Color.LightGray;<br>
  button1.Click += new EventHandler(button1_Click);<br>
 Label label2 = new Label();<br>
  label2.Text = "Low Guess";<br>
 label2.Bounds = new Rectangle(20, 150, 160, 40);<br>
label2.Font = new Font("Arial", 18);<br>
richTextBox1 = new RichTextBox();<br>
 richTextBox1.Bounds = new Rectangle(20, 190, 160, 300);<br>
 richTextBox1.Font = new Font("Arial", 16);<br>
Label label3 = new Label();<br>
label3.Text = "High Guess";<br>
 label3.Bounds = new Rectangle(180, 150, 160, 40);<br>
 label3.Font = new Font("Arial", 18);<br>
 richTextBox2 = new RichTextBox();<br>
 richTextBox2.Bounds = new Rectangle(180, 190, 160, 300);<br>
 richTextBox2.Font = new Font("Arial", 16);<br>
 label4 = new Label();<br>
 label4.Bounds = new Rectangle(20, 100, 340, 40);<br>
label4.Font = new Font("Arial", 16);<br>
 this.Controls.Add(label);<br>
 this.Controls.Add(textBox1);<br>
 this.Controls.Add(button1);<br>
 this.Controls.Add(label4);
this.Controls.Add(label2);<br>
 this.Controls.Add(label3);<br>
 this.Controls.Add(richTextBox1);<br>
 this.Controls.Add(richTextBox2);<br>


}<br>


   private void button1_Click(object sender, EventArgs e)<br>
 {<br>
  if (textBox1.Text == "")<br>
 {<br>
 return;<br>
 }<br>
 guessnum = Convert.ToInt32(textBox1.Text);<br>
 textBox1.Text = String.Empty;<br>
 if (win >= 0)<br>
 {<br>
if (guessnum == value)<br>
{<br>
MessageBox.Show("You have guessed the number! \n The number was " + value);<br>
InitializeComponent();<br>
 }<br>
 else if (guessnum < value)<br>
{
richTextBox1.Text += guessnum + "\n";<br>
  MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));<br>

 }<br>
else if (guessnum > value)<br>
 {<br>
richTextBox2.Text += guessnum + "\n";<br>
 MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));<br>

 }<br>
guess++;<br>
win--;<br>
}<br>
 if (guess == 11)<br>
 {<br>
 label4.Text = "You loose,Correct Guess is " + value;<br>
}<br>
 }<br>
 }<br>}<br>
Output:<br>
![Screenshot (36)](https://user-images.githubusercontent.com/99865138/159847645-2077ce51-e42f-4667-a118-8e25357f0354.png)<br>
![Screenshot (37)](https://user-images.githubusercontent.com/99865138/159847718-58060b06-6be7-4d24-93ed-ddff11a20da4.png)<br>
![Screenshot (38)](https://user-images.githubusercontent.com/99865138/159847803-965de7d3-7340-448a-a80a-fa11ffc38141.png)<br>

***************************************************************************************************************<br>
To create the binary Tree in window form application<br>
****************************************************************************************************************<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Drawing.Drawing2D;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace BinaryTree<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        private Node root;<br>
        public Form1()<br>
        {<br>
            InitializeComponent(<br>;<br>
            this.root = null;<br>
            test();<br>
        }<br>
        void test()<br>
        {<br>
            textBox1.Text = "5";<br>
            Add_Click(Add, null);<br>
            textBox1.Text = "3";<br>
            Add_Click(Add, null);<br>
            textBox1.Text = "2";<br>
            Add_Click(Add, null);<br>
            textBox1.Text = "1";<br>
            Add_Click(Add, null);<br>
            textBox1.Text = "4";<br>
            Add_Click(Add, null);<br>
            textBox1.Text = "7";<br>
            Add_Click(Add, null);<br>
            textBox1.Text = "6";<br>
            Add_Click(Add, null);<br>
            textBox1.Text = "8";<br>
            Add_Click(Add, null);<br>
        }<br>

      

        private void button2_Click(object sender, EventArgs e)<br>
        {<br>
            int value = int.Parse(textBox1.Text); if (root != null)<br>
            {<br>
                bool status = root.Remove(value, root, ref root); if (status == false)
                {<br>
                    MessageBox.Show("the value does not exists");<br>
                }<br>
            }<br>
            drawTree();<br>

        }<br>

        private void Add_Click(object sender, EventArgs e)<br>
        {<br>
            int value = int.Parse(textBox1.Text); if (root == null)<br>
                root = new Node(value);<br>
            else<br>
            {<br>
                if (root.Add(value) == false)<br>
                    MessageBox.Show("The value already exists!");<br>
            }<br>
            drawTree();<br>

        }<br>

        private void Create_Click(object sender, EventArgs e)<br>
        {<br>
            root = null;<br>
            pictureBox1.Image = null;<br>

        }<br>

        private void Search_Click(object sender, EventArgs e)<br>
        {<br>
            string msg;<br>
            int value = int.Parse(textBox1.Text); if (root == null)<br>
            {<br>
                msg = "Tree is empty";<br>
            }<br>
            else<br>
            {<br>
                if (root.Exists(value))<br>
                {<br>
                    msg = "Value found";<br>
                }<br>
                else<br>
                {<br>
                    msg = "Value not found";<br>
                }<br>
            }<br>
            MessageBox.Show(msg);<br>
        }<br>

 void drawTree()<br>
        {<br>
            if (root != null)<br>
                pictureBox1.Image = root.Draw();<br>
            else<br>
                pictureBox1.Image = null;<br>
            this.Update();<br>
        }<br>
      
    }<br>
    class Node<br>
    {
        internal Node left { get; set; }<br>
        internal Node right { get; set; }<br>
        internal int value;<br>
        internal int center = 12;<br>
        private static Bitmap nodeBg = new Bitmap(30, 25); private static Font font = new Font("Arial", 14);<br>
        internal Node(int value)<br>
        {<br>
            this.value = value;<br>
        }<br>
        internal bool Add(int value)<br>
        {<br>
            Node node = new Node(value);<br>
            if (value < this.value)<br>
            {<br>
                if (this.left == null)<br>
                {<br>
                    this.left = node;<br>
                    return true;<br>
                }<br>
                else<br>
                    return this.left.Add(value);<br>
            }<br>
            else if (value > this.value)<br>
            {<br>
                if (this.right == null)<br>

             {<br>
                    this.right = node;<br>
                    return true;<br>
                }<br>
 else<br>
                    return this.right.Add(value);<br>
            }
            return false;<br>
        }<br>
        internal bool Remove(int value, Node parent, ref Node root)<br>
        {<br>
            if (value < this.value)<br>
            {<br>
                if (left != null)<br>
                {<br>
                    return left.Remove(value, this, ref root);<br>
               <br>}<br>
            }<br>)<br>
            {<br>
                if (right != null)<br>
                {<br>
                    return right.Remove(value, this, ref root);<br>
                }<br>
            }<br>
            else if (value == this.value)<br>
            {<br>
                bool isLeft = (this == parent.left);<br>
                if (left == null && right == null)<br>
                {<br>
                    if (root == this)<br>
                        root = null;<br>
                    else<br>
                    if (isLeft) parent.left = null; else parent.right = null;<br>
                }<br>
                else if (right == null)<br>
                {<br>
                    if (isLeft) parent.left = left; else parent.right = left; if (root == this)<br>
                        root = left;<br>
                }<br>
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>

                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
        {<br>
            Size lSize = new Size(nodeBg.Width / 2, 0);<br>
            Size rSize = new Size(nodeBg.Width / 2, 0);<br>
            Image lNodeImg = null;<br>
            Image rNodeImg = null;<br>
            int lCenter = 0, rCenter = 0;<br>

            if (this.left != null)<br>
            {<br>
                lNodeImg = left.Draw();<br>
                lSize = lNodeImg.Size;<br>
                this.center = lSize.Width;<br>
                lCenter = left.center;<br>
            }<br>
            if (this.right != null)<br>
            {<br>
                rNodeImg = right.Draw();<br>
                rSize = rNodeImg.Size;
                rCenter = right.center;<br>
            }<br>
            int maxHeight = (lSize.Height < rSize.Height) ? rSize.Height : lSize.Height; if (maxHeight > 0) maxHeight += 35;<br>
<br>
        Size resultSize = new Size(lSize.Width + rSize.Width, nodeBg.Size.Height + maxHeight);<br>
            Bitmap result = new Bitmap(resultSize.Width, resultSize.Height);<br>
            Graphics g = Graphics.FromImage(result);<br>
            g.SmoothingMode = SmoothingMode.HighQuality;<br>
            g.FillRectangle(Brushes.White, new Rectangle(new Point(0, 0), resultSize)); g.DrawImage(nodeBg, lSize.Width - nodeBg.Width / 2, 0);<br>
            string str = "" + value;<br>
            g.DrawString(str, font, Brushes.Black, lSize.Width - nodeBg.Width / 2 + 7, nodeBg.Height / 2f - 12);<br>
            Pen pen = new Pen(Brushes.Black, 1.2f);<br>
            float x1 = center;<br>
            float y1 = nodeBg.Height;<br>
            float y2 = nodeBg.Height + 35;<br>
            float x2 = lCenter;<br>
            var h = Math.Abs(y2 - y1);<br>
            var w = Math.Abs(x2 - x1);<br>
            if (lNodeImg != null)<br>
            {<br>
                g.DrawImage(lNodeImg, 0, nodeBg.Size.Height + 35); var points1 = new List<PointF>
 {
 new PointF(x1, y1),<br>
 new PointF(x1 - w/6, y1 + h/3.5f),<br>
 new PointF(x2 + w/6, y2 - h/3.5f),<br>
 new PointF(x2, y2),<br>
 };<br>
                g.DrawCurve(pen, points1.ToArray(), 0.5f);<br>
            }<br>
            if (rNodeImg != null)<br>
            {<br>
                g.DrawImage(rNodeImg, lSize.Width, nodeBg.Size.Height + 35); x2 = rCenter + lSize.Width;<br>
                w = Math.Abs(x2 - x1);<br>
                var points = new List<PointF><br><br>
 {<br><br>
 new PointF(x1, y1),<br><br>
 new PointF(x1 + w/6, y1 + h/3.5f),<br><br>
 new PointF(x2 - w/6, y2 - h/3.5f),<br><br>
 new PointF(x2, y2)<br><br>
 };<br><br>

            g.DrawCurve(pen, points.ToArray(), 0.5f);<br><br>
            }<br><br>
            return result;<br><br>
        }<br><br>
        public bool Exists(int value)<br><br>
        {<br><br>
            bool res = value == this.value;<br><br>
            if (!res && left != null)<br><br>
                res = left.Exists(value);<br>
            if (!res && right != null)<br>
                res = right.Exists(value);<br>
            return res;<br>
        }<br>
    }<br>
} <br>
 Output: <br>
![Screenshot (38)](https://user-images.githubusercontent.com/99865138/161208961-4ffb6e0e-3848-4bbd-b7f0-7a52cd4105ff.png)<br>
 ![Screenshot (39)](https://user-images.githubusercontent.com/99865138/161209372-5f845c6c-36e9-40cb-9411-4db09d272d9e.png)<br>
************************************************************************************<br>
 Create note pad using window form application<br>
 ************************************************************************************<br>
 using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace notepad   <br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        private string fileName;<br>

        private RichTextBox txtContent;<br>
        private ToolBar toolBar;<br>
        internal Form1()<br>
        {<br>
            fileName = null;<br>
            InitializeComponents();<br>
        }<br>
        void InitializeComponents()<br>
        {<br>
            this.Text = "My notepad";<br>
            this.MinimumSize = new Size(600, 450);<br>
            this.FormClosing += new FormClosingEventHandler(NotepadClosing);<br>
            this.MaximizeBox = true;<br>
            toolBar = new ToolBar();<br>
            toolBar.Font = new Font("Arial", 16);<br>
            toolBar.Padding = new Padding(4);<br>
            toolBar.ButtonClick += new ToolBarButtonClickEventHandler(toolBarClicked);<br>
            ToolBarButton toolBarButton1 = new ToolBarButton();<br>
            ToolBarButton toolBarButton2 = new ToolBarButton();<br>
            ToolBarButton toolBarButton3 = new ToolBarButton();<br>
            toolBarButton1.Text = "New";<br><br>
            toolBarButton2.Text = "Open";<br>
            toolBarButton3.Text = "Save";<br>
            toolBar.Buttons.Add(toolBarButton1);<br>
            toolBar.Buttons.Add(toolBarButton2);<br>
            toolBar.Buttons.Add(toolBarButton3);<br>
            txtContent = new RichTextBox();<br>
            txtContent.Size = this.ClientSize;<br>
            txtContent.Height -= toolBar.Height;<br>
            txtContent.Top = toolBar.Height;<br>
            txtContent.Anchor = AnchorStyles.Left | AnchorStyles.Right |<br>
           AnchorStyles.Top | AnchorStyles.Bottom;<br>
            txtContent.Font = new Font("Arial", 16);<br>
            txtContent.AcceptsTab = true;<br>
            txtContent.Padding = new Padding(8);<br>

            this.Controls.Add(toolBar);<br>
            this.Controls.Add(txtContent);<br>
        }<br>
        private void toolBarClicked(Object sender, ToolBarButtonClickEventArgs e)<br>
        {<br>
            saveFile();<br>
            switch (toolBar.Buttons.IndexOf(e.Button))<br>
            {<br>
                case 0:<br>
                    this.Text += "My notepad";<br>
                    txtContent.Text = string.Empty;<br>
                    fileName = null;<br>
                    break;<br>
                case 1:<br>
                    OpenFileDialog openDlg = new OpenFileDialog();<br>
                    if (DialogResult.OK == openDlg.ShowDialog())<br>
                    {<br>
                        fileName = openDlg.FileName;<br>
                        txtContent.LoadFile(fileName);<br>
                        this.Text = "My notepad " + fileName;<br>
                    }<br>
                    break;<br>
            }<br>
        }<br>
        void saveFile()<br>
        {<br>
            if (fileName == null)<br>
            {<br>
                SaveFileDialog saveDlg = new SaveFileDialog();<br>
                if (DialogResult.OK == saveDlg.ShowDialog())<br>
                {<br>
                    fileName = saveDlg.FileName;<br>
                    this.Text += " " + fileName;<br>
                }<br>
            }<br>
            else<br>
            {<br>
                txtContent.SaveFile(fileName, RichTextBoxStreamType.RichText);<br>
            }<br>
        }<br>
        private void NotepadClosing(Object sender, FormClosingEventArgs e)<br>
        {<br>
            saveFile();<br>
        }<br>
        static void main(String[] args)<br>
        {<br>
 Application.Run(new Form1());<br>
        }<br>
    }<br>
}<br>
output:<br>
 ![Screenshot (41)](https://user-images.githubusercontent.com/99865138/161209742-d5fa1070-705e-4a53-89a2-fbdc227baf2d.png)<br>
 
