# flask-microblog
        [DllImport("user32.dll", CharSet = CharSet.Auto, SetLastError = false)]
        private static extern int SendMessage(IntPtr hWnd, uint msg, IntPtr wParam, string lParam);
        [DllImport("User32.dll", EntryPoint = "FindWindow")]
        public static extern IntPtr FindWindow(string lpClassName, string lpWindowName);
        [DllImport("User32.dll", EntryPoint = "FindWindowEx")]
        public static extern IntPtr FindWindowEx(IntPtr hwndParent, IntPtr hwndChildAfter, string lpClassName, string lpWindowName);

        private void button2_Click(object sender, EventArgs e)
        {
            IntPtr x = new IntPtr();
            IntPtr parent = FindWindow(null, "test.txt - 记事本");
            IntPtr child = FindWindowEx(parent, x, "Edit", null);
            SendMessage(child, WM_SETTEXT, IntPtr.Zero, textBox1.Text);
        }