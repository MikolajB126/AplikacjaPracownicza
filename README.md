using System.Windows;

namespace AplikacjaMailowa
{
    public partial class LoginWindow : Window
    {
        public LoginWindow()
        {
            InitializeComponent();
        }

        private void Login_Click(object sender, RoutedEventArgs e)
        {
            MessageBox.Show("Logowanie zakończone sukcesem");
            MainWindow main = new MainWindow();
            main.Show();
            this.Close();
        }

        private void Register_Click(object sender, RoutedEventArgs e)
        {
            MessageBox.Show("Rejestracja zakończona sukcesem");
            MainWindow main = new MainWindow();
            main.Show();
            this.Close();
        }
    }
}
