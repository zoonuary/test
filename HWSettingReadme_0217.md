
  # HPT.Utilities 기능 모듈
  
각 모듈이 공통적으로 사용하는 공용 UI 컴포넌트를 모아놓은 모듈

# 필요 사항

# 주요 기능

# UI
## HWSetting


## 비동기 데이터 처리 
로깅 파일을 읽거나 쓰는 도중에 쓰레드가 중단되는 현상을 방지하기 위해  
쓰레딩 또는 Async, Await 비동기 처리, BackGroundWorker 등을 사용하여  
최적화가 필요하다.

- BackGroundWorker 클래스를 통한 비동기 데이터 처리  
https://learn.microsoft.com/ko-kr/dotnet/api/system.componentmodel.backgroundworker?view=net-8.0

## 외부 모듈과의 연결
파일에 읽고 쓰는 것 자체는 해당 모듈에서 처리하면 되지만, 읽는 기능의 경우 그 결과를 출력 해야 한다.  
읽는 중 일어나는 Parsing 알고리즘을 통해서 공용 데이터(EventData)가 생성되면 해당 데이터를
외부 모듈에게 전달할 수 있는 기능을 제공한다.

이를 위해서 Common 모듈에서 제공하는 기능을 활용하거나 BackGroundWorker를 통해서 연결할 수 있다.

> 모듈을 Application위에 올려 테스트하는 과정에서 최적화가 필요

- HPT.Common 모듈의 "EventHandlerManager" 클래스 활용하여 Parsing 된 데이터 전달
- BackGroundWorker를 통해 외부 모듈에 Parsing 진행상황 전달

참고 자료 : https://www.csharpstudy.com/WinForms/WinForms-backgroundworker.aspx
