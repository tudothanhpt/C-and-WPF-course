# C# OOP - Lập trình hướng đối tượng
OOP – (Object-Oriented Programming) là viết tắt của lập trình hướng đối tượng.

Lấy đối tượng làm nền tảng xây dựng phần mềm dựa trên các lớp (Class) và đối tượng (Object)

Một đối tượng (Object) gồm có thuộc tính (Fied) và Phương thức (Method)

Các lớp (Class) để gom các đối tượng có cùng đặc tính, trong một Class cũng gồm thuộc tính và phương thức.

Class cũng được dùng để định nghĩa kiểu dữ liệu mới.

## Phạm vi truy cập
1. public : truy cập ở mọi nơi

2. private : Chỉ dùng nội bộ trong Class.

3. protected :  chỉ dùng nội bộ trong Class, ngoài ra có thể truy cập từ Class kế thừa

4. internal : Chủ dùng trong Assembly (dự án đó)

5. Không khai báo phạm vi thì mặc định Class là internal
6. Các thành phần trong Class nếu không khai báo phạm vi thì mặc định là private

## Khai báo biến

```C#
<kiểu biến> <tên biến> = <giá trị>
//---
string name = "BIMSoft";
int myNum = 15;
double myNum = 5.99d;
float myNum = 0.7f;
bool mybool = true;
```

## Đặc tính (Get and Set)
```C#
class User
{
  private string name; // field

  public string Name   // property
  {
    get { return name; }   // get method
    set { name = value; }  // set method
  }
}
```

```C#
class User
{
    public string Name { get; set; }
}
```
## Khai báo Command
```C#
private class TenLenh : ICommand
{
    public bool CanExecute(object parameter)
    {
        return true;
    }
    public event EventHandler CanExecuteChanged
    {
        add { CommandManager.RequerySuggested += value; }
        remove { CommandManager.RequerySuggested -= value; }
    }

    public async void Execute(object parameter)
    {
        ...
    }
}
```