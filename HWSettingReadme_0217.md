
  # HPT.Utilities 기능 모듈
  
각 모듈이 공통적으로 사용하는 공용 UI 컴포넌트를 모아놓은 모듈

# 필요 사항



# 주요 기능



# UI
## HWSetting
- UI 위치 : HPT.Utilities\HWSetting

- 필요 사항 : 사용하고자하는 main winform 프로젝트에서 HPT.Utilities 참조

#### User Control 가져오기

##### Winform
``` C# (Devexpress)
private void HWSettingOpener_ItemClick(object sender, DevExpress.XtraBars.ItemClickEventArgs e)
{
    XtraForm HWSettingForm = new XtraForm
    {
        Text = "HWSetting",
        Width = 800,
        Height = 600
    };
    HWSettingForm.Controls.Add(new ElementHost
    {
        Dock = DockStyle.Fill,
        Child = new HwSettingView()
    });
    HWSettingForm.ShowDialog();
}
```
##### WPF
```C#
// MainWindow의 ViewModel에서 생성
public void OpenHWSettingDialog()
{
    ThemedWindow hwSettingWindow = new ThemedWindow
    {
        Title = "HW_Settings",
        Width = 800,
        Height = 600
    };
    hwSettingWindow.Content = new HwSettingView
    {
        VerticalAlignment = VerticalAlignment.Stretch,
        HorizontalAlignment = HorizontalAlignment.Stretch
    };
    hwSettingWindow.ShowDialog();
}

```

