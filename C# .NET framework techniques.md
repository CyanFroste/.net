#### In C# .net framework THE MAIN FORM CAN'T BE CLOSED USING this.Close();

### USING THREAD TO OPEN FORMS
```
var formOneThread = new Thread(() => Application.Run(new FormOne()));
formOneThread.Start();
System.Windows.Forms.Application.ExitThread();
this.Close();
```
### LOGIN USING A DIALOG FORM
In Program.cs
```
LoginForm fLogin = new LoginForm();
if (fLogin.ShowDialog() == DialogResult.OK)
{
    Application.Run(new MainForm());
}
else
{
    Application.Exit();
}
```            
In LoginForm.cs
```
if (login condition)
{
    this.DialogResult = DialogResult.OK;
    this.Close();
}
else
{
    MessageBox.Show("Login Failed");
}
```
