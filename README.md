<Window x:Class="AplikacjaMailowa.LoginWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Logowanie" Height="300" Width="400" WindowStartupLocation="CenterScreen">
    <Grid Margin="20">
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto"/>
            <ColumnDefinition Width="*"/>
        </Grid.ColumnDefinitions>

        <Label Grid.Row="0" Grid.Column="0" Content="Login:" VerticalAlignment="Center" Margin="0,5"/>
        <TextBox x:Name="UsernameBox" Grid.Row="0" Grid.Column="1" Width="200" Margin="5"/>

        <Label Grid.Row="1" Grid.Column="0" Content="Hasło:" VerticalAlignment="Center" Margin="0,5"/>
        <PasswordBox x:Name="PasswordBox" Grid.Row="1" Grid.Column="1" Width="200" Margin="5"/>

        <Label Grid.Row="2" Grid.Column="0" Content="Email:" VerticalAlignment="Center" Margin="0,5"/>
        <TextBox x:Name="EmailBox" Grid.Row="2" Grid.Column="1" Width="200" Margin="5"/>

        <StackPanel Grid.Row="3" Grid.ColumnSpan="2" Orientation="Horizontal" HorizontalAlignment="Center" Margin="0,10">
            <Button Content="Loguj" Width="100" Margin="10,0" Click="Login_Click"/>
            <Button Content="Rejestruj" Width="100" Margin="10,0" Click="Register_Click"/>
        </StackPanel>
    </Grid>
</Window>
