
# HPT.HWSetting 모듈
모듈로 불러온 UI 구조

![HWSetting구조이미지](https://github.com/user-attachments/assets/1a7c2035-5dd6-4140-b7d2-a73fe724d070)


# 패턴 및 폴더 구조
#### 패턴 : MVVM
#### 폴더 구조
코드 비하인드(.xaml.cs)는 나타내지 않음
```bash
├── Views/
│   ├── MainWindow.xaml
│   ├── Controls/
│   │   ├── ChannelTree.xaml
│   │   └── Toolbar.xaml
│   └── Pages/
│       ├── Channels/
│       │   ├── CANChannel.xaml
│       │   ├── LINChannel.xaml
│       │   └── ETHChannel.xaml
│       └── Setups/
│           ├── CANSetup.xaml
│           ├── LINSetup.xaml
│           └── ETHSetup.xaml
│
├── ViewModels/   <- Views 디렉토리와 같은 구조로 진행
│   ├── '''
│   └── '''
│
└── Models/
    ├── COMMON.cs
    ├── Channels/
    │   ├── CANChannelData.cs
    │   ├── LINChannelData.cs
    │   └── ETHChannelData.cs
    └── Setups/
        ├── CANSetupData.cs
        ├── LINSetupData.cs
        └── ETHSetupData.cs
```

# Model
> #### COMMON.cs
> > 데이터를 일괄적으로 관리하고 처리하는 클래스.
> >
> > DataModel에 있는 모든 모델의 클래스타입 및 데이터를 알고있으며 xaml 파일의 데이터 바인딩 소스.
> > 
> > 특정 Model의 Data property가 변경 시, 변경 전 상태를 임시 DataModel로 생성하여 List에 추가하는 방식으로 저장했다가, window가 닫히기 전 상황에 맞게 처리
> #### Channel/
> > channel 자체에 대한 세팅값을 가지고있는 DataModel
> #### Setup/
> > 특정 채널(CAN1, CAN2 등)에 대한 세팅값을 가지는 DataModel 

# View
> #### MainWindow.xaml
> > dll 모듈 호출 시 생성되게 될 WPF window.
> > Control 들을 호출하고 관리
> > #### Controls/
> > > #### ChannelTree.xaml
> > > 현재 하드웨어 채널을 보여주는 컨트롤
> > > #### ToolBar.xaml
> > > driver 정보 / 설정값 저장 / 닫고 나가기 등의 동작기능을 수행하는 Bar
> > #### Pages/
> > ChannelTree에서 고른 채널의 타입이나 특정 채널에 대해 세팅값을 제어할 수 있는 페이지들의 모음
> >
> > Navigation Frame 을 이용한 페이지 동적 로딩
> > > #### Channels/
> > > 채널에 대한 페이지
> > > #### Setups/
> > > 특정 채널의 상세 세팅 페이지


### 추가 질문/조율 내용

* DataProperty AutoNotifySystem
    * NotifyPropertyChanges -> Dx) OnPropertyChanged, GetProperty(), SetProperty()
        * 데이터 프로퍼티의 propertychange방법에 대한 코드적 통일이 필요한지
* window를 어디에서 생성할 지
    * dll 에서 창을 로드 -> (Themedwindow의 경우) MahApps.Metro dll 필요
    * Main App에서 직접 창을 생성하고 dll은 UserControl을 불러올지
* DataContext
    * code behind에서 주입
    * xaml에서 주입
* Model의 설계 부분 (피드백 내용에 따라 질문사항이 안 될 수 있음)
    * 데이터를 들고있는 클래스를 Model이라고 해도 되는지 ( => DataContainer?)
    * Common.cs 의 경우 Model 타입별 데이터를 일괄적으로 관리하고 처리하는 DataSource의 역할을 함  
