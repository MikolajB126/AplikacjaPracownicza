using System.Collections.Generic;
using System.Windows;

namespace AplikacjaMailowa
{
    public class User
    {
        public string Password { get; set; }
        public string Email { get; set; }
        public User(string password, string email)
        {
            Password = password;
            Email = email;
        }
    }

    public partial class LoginWindow : Window
    {
        public static Dictionary<string, User> Users = new Dictionary<string, User>();
        public static string CurrentUserEmail { get; set; }

        static LoginWindow()
        {
            Users["admin"] = new User("1234", "admin@example.com");
        }

        public LoginWindow()
        {
            InitializeComponent();
        }

        private void Login_Click(object sender, RoutedEventArgs e)
        {
            string username = UsernameBox.Text;
            string password = PasswordBox.Password;

            if (Users.TryGetValue(username, out var user) && user.Password == password)
            {
                CurrentUserEmail = user.Email;
                MainWindow main = new MainWindow();
                main.Show();
                this.Close();
            }
            else
            {
                MessageBox.Show("Błędny login lub hasło");
            }
        }

        private void Register_Click(object sender, RoutedEventArgs e)
        {
            string username = UsernameBox.Text;
            string password = PasswordBox.Password;
            string email = EmailBox.Text;

            if (string.IsNullOrWhiteSpace(username) || string.IsNullOrWhiteSpace(password) || string.IsNullOrWhiteSpace(email))
            {
                MessageBox.Show("Wypełnij wszystkie pola");
                return;
            }

            if (!Users.ContainsKey(username))
            {
                Users[username] = new User(password, email);
                MessageBox.Show("Rejestracja zakończona sukcesem");
            }
            else
            {
                MessageBox.Show("Użytkownik już istnieje");
            }
        }
    }
}
