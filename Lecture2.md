## Đối tượng ViewModel

```C#
class SignInViewModel : PropertyChangedBase
{
    private string _maMayTinh = Encrypt(JsonConvert.SerializeObject(new ComInfo()),"PassWPF1");
    public string MaMayTinh
    {
        get
        {
            return _maMayTinh;
        }
        set
        {
            _maMayTinh = value;
            OnPropertyChanged("MaMayTinh");
        }
    }
}
```

## Định nghĩa DataContext
```C#
class DataContext
{
    public static SignInViewModel DcSignIn = new SignInViewModel();
}

```

## View áp dụng

```C#
<Window ...
        xmlns:vm="clr-namespace:VIPApp.aViewModel"
        d:DataContext="{d:DesignInstance Type=vm:SignInViewModel}"
        ...>
    <Grid>
        ...
    </Grid>
</Window>
```

## View Code-Behide
```C#
public SignIn()
{
    this.DataContext = DcSignIn;
    InitializeComponent();
}
```