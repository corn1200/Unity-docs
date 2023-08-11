# Unity-docs

# 목차
* [1. 개요](#1-개요)
* [2. 개념](#2-개념)
    * [2.1. 게임 오브젝트](#21-게임-오브젝트)
    * [2.2. 컴포넌트](#22-컴포넌트)
    * [2.3. 씬](#23-씬)
    * [2.4. 에셋](#24-에셋)
    * [2.5. 스크립트](#25-스크립트)
    * [2.6. 물리 엔진](#26-물리-엔진)
    * [2.7. 네트워킹](#27-네트워킹)
* [3. 유니티 생명주기](#3-유니티-생명주기)
    * [3.1. Awake vs Start](#31-awake-vs-start)
    * [3.2. Update vs FixedUpdate vs LateUpdate](#32-update-vs-fixedupdate-vs-lateupdate)
* [4. C# & Unity](#4-c--unity)
    * [4.1. 박싱 & 언박싱](#41-박싱--언박싱)
    * [4.2. 직렬화 & 역직렬화](#42-직렬화--역직렬화)
    * [4.3. const vs readonly](#43-const-vs-readonly)
    * [4.4. string](#44-string)
    * [4.5. Garbage Collecto](#45-garbage-collector)
    * [4.6. delegate & event](#46-delegate--event)
    * [4.7. this](#47-this)
    * [4.8. List, Dictionary 등 자료구조의 내부](#48-list-dictionary-등-자료구조의-내부)
    * [4.9. C# vs C++](#49-c-vs-c)
* [5. 로컬 좌표 & 월드 좌표](#5-로컬-좌표--월드-좌표)
    * [5.1. 로컬 회전 & 월드 회전 ](#51-로컬-회전--월드-회전)
* [6. 센터 & 피벗](#6-센터--피벗)
* [7. 기즈모](#7-기즈모)
* [8. 회전](#8-회전)
* [9. 이동](#9-이동)
* [10. 리지드 바디](#10-리지드-바디)
* [11. 콜라이더](#11-콜라이더)

# 1. 개요
유니티 엔진은 게임 개발과 시뮬레이션을 위한 종합적인 크로스 플랫폼 게임 엔진이다.   
Unity Technologies에서 개발하고 유지 관리하며, 2005년에 처음 출시되었다.    
초기에는 주로 인디 게임 개발자들이 사용했지만, 시간이 흐르면서 많은 큰 회사와 AAA급 게임 제작에도 널리 사용되고 있다.

1. 크로스 플랫폼 지원: Unity는 Windows, macOS, Linux 등의 데스크톱 운영체제부터 iOS, Android, 콘솔 게임 기기, 웹 브라우저, VR/AR 디바이스까지 다양한 플랫폼을 지원한다.     
이러한 특성으로 한 번의 개발로 다양한 플랫폼으로 게임을 배포할 수 있다.
2. 사용자 친화적인 인터페이스: Unity는 쉽고 직관적인 사용자 인터페이스를 제공하여 개발자들이 쉽게 게임 개발에 참여할 수 있도록 돕는다.  
비전문가 개발자들에게도 접근하기 쉬운 툴을 제공하여 게임 제작의 기술적 장벽을 낮추는 데 도움이 된다.
3. 스크립트 언어: Unity는 주로 C# 스크립트를 사용하여 게임 로직을 구현한다.     
C#은 사용하기 쉽고 강력한 객체 지향 프로그래밍 언어로, 개발자들이 게임 오브젝트의 동작과 상호작용을 정의하는 데에 자주 활용된다.
4. 에셋과 에셋 스토어: Unity는 게임에 필요한 자원들을 "에셋"이라고 부른다.  
이러한 에셋들은 3D 모델, 텍스처, 애니메이션, 사운드, 스크립트 등으로 구성된다.  
Unity Asset Store를 통해 다른 개발자들이 제작한 에셋들을 구매하거나 판매할 수 있어, 개발 속도를 높이고 자원을 재활용할 수 있다.
5. 2D 및 3D 지원: Unity는 2D 및 3D 게임을 모두 지원한다.    
2D 게임 개발에 필요한 도구와 기능을 제공하며, 3D 게임 개발에서는 강력한 물리 시뮬레이션과 애니메이션 시스템을 사용할 수 있다.
6. 물리 엔진: Unity는 물리 엔진을 내장하고 있어, 게임 오브젝트들의 움직임과 충돌을 현실적으로 시뮬레이션할 수 있다.
7. 네트워킹 지원: Unity는 멀티플레이어 게임을 개발하기 위한 네트워킹 기능을 제공하여 여러 플레이어가 게임 세계를 함께 공유할 수 있도록 한다.

유니티 엔진은 이러한 특징과 개념을 통해 개발자들이 다양한 플랫폼에 게임을 빠르고 효율적으로 개발할 수 있도록 지원하며, 게임 개발의 접근성과 생산성을 높이는데 큰 역할을 한다.

# 2. 개념
유니티 엔진의 개념은 게임 개발과 시뮬레이션을 위한 기초적인 이해를 제공한다.    
다음은 유니티 엔진의 주요 개념에 대한 설명이다:

1. 게임 오브젝트(Game Objects): 유니티에서 모든 요소는 게임 오브젝트로 표현된다.    
게임 오브젝트는 캐릭터, 물체, 카메라, 조명 등 게임 월드의 모든 요소를 나타내는 기본 단위이다.   
각각의 게임 오브젝트는 위치, 회전, 크기 등을 가지고 있으며, 이들을 조작하여 게임 세계를 구성하고 상호작용을 만들어낸다.
2. 컴포넌트(Components): 게임 오브젝트는 기능을 갖는 다양한 컴포넌트들의 조합으로 이루어진다.   
예를 들어, 물리 엔진을 적용하려면 물리 컴포넌트를 추가하고, 움직임을 제어하려면 스크립트 컴포넌트를 추가한다.   
각 컴포넌트는 게임 오브젝트의 동작과 시각적 표현 등을 결정한다.
3. 씬(Scenes): 씬은 게임을 구성하는 하나의 환경 또는 레벨을 나타낸다.   
씬은 게임 오브젝트와 컴포넌트들의 계층 구조로 구성되며, 게임 플레이를 구성하는 모든 내용을 담고 있다.   
각 씬은 독립적으로 로드하거나 언로드할 수 있으므로, 다양한 레벨과 환경을 만들 수 있다.
4. 에셋(Assets): 유니티에서 사용되는 모든 자원들을 에셋이라고 한다.     
이러한 자원은 3D 모델, 텍스처, 사운드 파일, 애니메이션, 스크립트 등을 포함한다.     
에셋은 게임 개발에 필수적이며, Unity Asset Store에서는 개발자들이 다른 사용자들과 자원을 공유하고 구매할 수 있다.
5. 스크립트(Scripts): 유니티에서는 C#을 주로 사용하여 게임 오브젝트의 동작을 정의하는 스크립트를 작성한다.  
스크립트는 게임 오브젝트에 부착된 컴포넌트로, 게임 로직, 사용자 입력 처리, 인공지능, 특수 효과 등을 구현하는 데 사용된다.
6. 물리 시뮬레이션(Physics Simulation): 유니티는 물리 엔진을 내장하여 게임 오브젝트들이 중력, 충돌, 운동 등의 물리적 특성을 가질 수 있다.   
이를 통해 게임 월드의 현실성과 물리적 효과를 구현할 수 있다.
7. 네트워킹(Networking): 유니티는 멀티플레이어 게임을 개발하기 위한 네트워킹 기능을 지원한다.   
이를 통해 여러 플레이어가 동시에 게임 세계를 공유하고 상호작용할 수 있다.

# 2.1. 게임 오브젝트
유니티 엔진의 게임 오브젝트 작동 원리는 게임 오브젝트의 생성, 업데이트, 렌더링 등의 주요 단계로 이루어진다.     
각 게임 오브젝트는 개별적으로 동작하면서 게임 세계를 형성하고, 이들의 상호작용으로 게임이 진행된다.     
다음은 유니티 엔진 게임 오브젝트의 작동 원리를 단계별로 설명한다:

1. 생성(Creation): 게임 오브젝트는 유니티에서 씬(Scene)에 배치하거나 스크립트를 통해 동적으로 생성할 수 있다.   
오브젝트의 생성은 Instantiate() 함수를 호출하거나 에디터에서 오브젝트를 드래그 앤 드롭하여 이루어진다.  
각 게임 오브젝트는 고유한 이름과 초기 속성(위치, 회전, 크기)을 가지며, 트랜스폼(Transform) 컴포넌트를 통해 이러한 정보를 관리한다.
2. 업데이트(Update): 게임 오브젝트는 프레임 단위로 업데이트된다.    
이는 게임 오브젝트의 위치, 회전, 애니메이션, 물리 시뮬레이션 등이 매 프레임마다 변경될 수 있음을 의미한다.  
게임 오브젝트의 업데이트는 MonoBehaviour 스크립트 컴포넌트를 통해 이루어지며, 이 스크립트들은 유니티 엔진에서 지정된 순서대로 호출되어 실행된다.    
Update() 함수를 사용하여 프레임마다 실행되는 로직을 구현할 수 있다.
3. 렌더링(Rendering): 게임 오브젝트는 3D 렌더링 과정을 거쳐 화면에 표시된다.    
렌더링은 유니티 엔진의 그래픽 파이프라인을 통해 이루어지며, 게임 오브젝트의 3D 모델, 텍스처, 조명, 카메라 설정 등이 고려되어 화면에 출력된다.   
렌더링은 각 게임 오브젝트가 카메라에 따라 시점에 따라 보여지는 순서와 방식을 결정한다.
4. 상호작용(Interaction): 게임 오브젝트는 사용자와 상호작용하거나 다른 게임 오브젝트들과 상호작용할 수 있다.    
이를 구현하기 위해 개발자는 유니티의 콜라이더(Collider) 컴포넌트와 물리 시스템을 사용하여 충돌 검사를 하거나, 스크립트를 통해 사용자 입력에 따른 반응을 구현한다.
5. 파괴(Destruction): 게임 오브젝트는 더 이상 필요하지 않을 때 파괴될 수 있다.  
Destroy() 함수를 호출하거나 특정 조건을 만족할 때 게임 오브젝트를 파괴하는 로직을 작성한다.

이러한 단계들로 구성된 게임 오브젝트의 작동 원리는 유니티 엔진에서 게임 세계를 구현하고 제어하는 데에 중요한 역할을 한다.   

# 2.2. 컴포넌트
유니티 엔진의 컴포넌트(Component)는 게임 오브젝트의 기능을 정의하고 제어하는 데 사용되는 모듈화된 요소이다.     
각각의 게임 오브젝트는 여러 개의 컴포넌트들을 가질 수 있으며, 이들 컴포넌트들은 게임 오브젝트의 동작과 시각적 표현, 상호작용 등을 결정한다.     
컴포넌트의 작동 원리를 설명하려면 아래의 주요 포인트들을 고려해야 한다:

1. 컴포넌트의 추가: 유니티에서 컴포넌트는 에디터를 통해 게임 오브젝트에 추가할 수 있다.     
에디터에서 오브젝트를 선택하고, 컴포넌트를 추가하고자 하는 컴포넌트 목록에서 선택하면 된다.     
또한 스크립트로 컴포넌트를 동적으로 추가하는 것도 가능하다.
2. 컴포넌트의 초기화: 컴포넌트가 게임 오브젝트에 추가되면, Awake()와 Start()와 같은 초기화 함수들이 호출된다.   
이 함수들은 컴포넌트의 상태를 초기화하거나, 다른 컴포넌트나 게임 오브젝트와의 연결을 설정하는 등의 작업을 수행한다.
3. 제어와 행위 분리: 컴포넌트 기반 설계의 장점은 제어와 행위를 분리할 수 있다는 점이다.     
즉, 각 컴포넌트는 독립적으로 작동하며, 필요에 따라 추가/제거/교체가 가능하다.   
이로 인해 코드의 재사용성이 증가하고 개발자들은 높은 수준의 모듈화를 이뤄낼 수 있다.
4. 컴포넌트 간 통신: 컴포넌트들은 서로간에 통신을 할 수 있으며, 이를 통해 게임 오브젝트의 동작을 복잡하게 조합하고 상호작용할 수 있다.  
이는 개발자들이 유연하고 다양한 게임 플레이 시나리오를 구현할 수 있도록 돕는다.

유니티 엔진에서 컴포넌트의 작동 원리는 게임 개발의 핵심 원리 중 하나로, 각 컴포넌트들이 조합되어 게임의 동작과 시각적인 표현, 상호작용을 결정한다.  

# 2.3. 씬
유니티 엔진의 씬(Scene)은 게임 세계를 구성하는 하나의 환경 또는 레벨을 나타내며, 게임 오브젝트들과 다른 리소스들을 담고 있는 컨테이너이다.  
씬은 게임을 구성하는 기본 단위로서, 각각의 씬은 독립적으로 로드하거나 언로드할 수 있다.     
이를 통해 다양한 레벨과 환경을 만들고 게임 흐름을 관리할 수 있다.   
유니티 엔진에서 씬의 작동 원리는 아래와 같은 순서로 진행된다:

1. 씬의 생성 및 로드: 씬은 유니티 프로젝트에 생성되고 저장된다.     
유니티 에디터를 통해 새로운 씬을 생성하거나 기존의 씬을 로드할 수 있다.     
또는 게임 실행 중에 동적으로 씬을 로드할 수도 있다.
2. 게임 오브젝트 배치: 씬은 게임 오브젝트들을 배치하는 공간이다.    
에디터를 사용하여 게임 오브젝트들을 씬에 배치하거나 스크립트를 통해 동적으로 생성할 수 있다.    
게임 오브젝트는 씬의 내용을 구성하는 주요 요소이며, 각각의 게임 오브젝트는 해당하는 컴포넌트들을 가지고 있다.
3. 컴포넌트 초기화: 씬에 배치된 각 게임 오브젝트의 컴포넌트들은 Awake() 함수를 통해 초기화된다.     
이 함수는 컴포넌트가 생성될 때 한 번만 호출되며, 컴포넌트의 상태를 초기화하거나 다른 컴포넌트나 오브젝트와의 연결을 설정하는 등의 작업을 수행한다.
4. 씬 전환: 유니티 엔진은 여러 개의 씬을 로드하고 전환할 수 있다.   
특정 이벤트에 따라 다른 씬으로 전환하거나, 다른 씬을 동적으로 로드하여 게임 흐름을 제어할 수 있다.
5. 씬의 저장과 언로드: 에디터에서 작업한 씬은 프로젝트에 저장되며, 게임 실행 중에는 불필요한 씬을 언로드하여 메모리 관리에 유리하게 한다.

이러한 과정을 거쳐 유니티 엔진의 씬은 게임 개발에서 중요한 역할을 한다.     
씬을 잘 구성하고 관리하면 게임의 흐름과 세계를 효과적으로 제어하고 구현할 수 있다.

# 2.4. 에셋
유니티 엔진 에셋(Assets)은 게임 개발에 사용되는 모든 자원들을 말한다.   
이는 3D 모델, 텍스처, 사운드 파일, 애니메이션, 스크립트 등 다양한 유형의 자원들을 포함한다.     
에셋은 게임 오브젝트에 부착된 컴포넌트처럼 동작하지 않으며, 게임 세계의 구성과 기능을 결정하는 것보다는 게임 개발의 재료로 사용된다.    
유니티 엔진의 에셋은 다음과 같은 작동 원리로 동작한다:

1. 에셋의 생성과 가져오기: 유니티 프로젝트 내에서 새로운 에셋을 생성하거나 기존의 에셋을 가져올 수 있다.    
에셋을 프로젝트 내 적절한 폴더에 추가하고 구성한다.
2. 에셋의 인스턴스화: 에셋을 프로젝트에서 씬으로 끌어와서 사용하면, 씬에 에셋의 인스턴스가 생성된다.    
이 인스턴스는 씬에 속한 개별적인 오브젝트로서 동작하며, 기존 에셋의 변경에 영향을 받지 않는다.
3. 에셋의 연결과 참조: 에셋은 게임 오브젝트의 컴포넌트에 연결되거나 스크립트에서 참조될 수 있다.    
예를 들어, 3D 모델 에셋은 게임 오브젝트에 Mesh Renderer 컴포넌트로 연결되어 시각적인 모습을 결정하거나, 스크립트에서 로드되어 특정 동작을 수행할 수 있다.
4. 에셋의 빌드: 게임을 빌드할 때, 프로젝트의 에셋들은 최적화 및 압축 등의 처리를 거쳐 게임 패키지로 포함된다.   
이는 게임이 실행될 때 자원을 효율적으로 사용할 수 있도록 한다.
5. 에셋 번들: 에셋 번들은 게임을 런타임에서 동적으로 로드하는 데에 사용되는 패키지이다.     
게임에 필요한 에셋들을 번들로 묶어서 원격으로 다운로드하거나 게임 실행 중에 로드하여 효율적인 에셋 관리를 가능하게 한다.

유니티 엔진의 에셋은 게임 개발 과정에서 매우 중요한 요소로 작동한다.    
잘 구성된 에셋은 게임의 품질과 성능을 향상시키고, 개발 시간을 단축하며, 개발자들이 공동으로 작업하고 에셋을 공유하는 데에도 도움을 준다.

# 2.5. 스크립트
유니티 엔진에서 스크립트(Script)는 게임 오브젝트의 동작과 상호작용, 게임 로직 등을 정의하고 구현하는 데 사용된다.   
스크립트는 주로 C# 언어를 사용하여 작성되며, 개발자들은 스크립트를 통해 게임 오브젝트의 행동을 제어하고 게임의 동작을 구현한다.     
스크립트의 작동 원리는 아래와 같은 순서로 이루어진다.

1. 스크립트의 생성과 추가: 개발자는 유니티 프로젝트 내에서 새로운 스크립트를 생성하거나 기존의 스크립트를 가져와서 사용할 수 있다.  
스크립트는 에디터를 통해 게임 오브젝트에 추가되어 동작하게 된다.
2. 스크립트의 구현: 스크립트는 C# 언어를 사용하여 구현된다.     
개발자들은 해당 스크립트 파일을 에디터나 외부 코드 편집기에서 열어서 로직과 기능을 작성한다.    
스크립트는 MonoBehaviour 클래스를 상속받아 유니티 엔진과 상호작용할 수 있다.
3. 스크립트의 컴포넌트로서의 동작: 스크립트는 게임 오브젝트에 컴포넌트로 추가되어 동작한다.     
MonoBehaviour 클래스를 상속받았기 때문에, 스크립트는 해당 게임 오브젝트의 컴포넌트로서 업데이트 함수(Update(), FixedUpdate(), LateUpdate())를 갖게 되어 프레임마다 동작을 처리할 수 있다.
4. 게임 오브젝트와의 상호작용: 스크립트는 게임 오브젝트와 상호작용하여 게임의 동작을 제어한다.  
스크립트는 게임 오브젝트의 트랜스폼(Transform)을 변경하여 위치, 회전, 크기 등을 조정하거나, 다른 컴포넌트들과 상호작용하여 게임 오브젝트의 동작을 결정한다.
5. 사용자 입력 처리: 스크립트는 사용자의 입력을 처리하여 게임 오브젝트의 동작을 변화시킬 수 있다.   
마우스 클릭, 키보드 입력 등을 감지하고 이를 처리하여 게임의 플레이어 상호작용을 구현한다.
6. 상태 및 변수 관리: 스크립트는 변수를 사용하여 게임 오브젝트의 상태와 속성을 저장하고 관리한다.   
변수는 스크립트의 필드로 선언되며, 게임의 진행과 상호작용에 따라 값이 변경될 수 있다.
7. 이벤트 처리: 스크립트는 이벤트를 사용하여 특정 조건이 발생했을 때 특정 동작을 수행할 수 있다.    
예를 들어 충돌이 발생했을 때, 타이머가 만료되었을 때 등의 이벤트를 처리할 수 있다.

유니티 엔진의 스크립트는 게임 개발에서 중요한 역할을 수행하며, 게임의 동작을 제어하고 구현하는 데에 큰 영향을 미친다.

# 2.6. 물리 엔진
유니티의 물리 엔진은 게임 세계에서 물리적인 동작을 시뮬레이션하고 게임 오브젝트들 간의 상호작용을 처리하는 역할을 담당한다.     
물리 엔진은 게임 오브젝트의 움직임, 충돌, 중력 등과 같은 물리적인 요소들을 모사하여 현실적인 동작을 제공한다.   
이를 통해 게임에서 물체들이 자연스럽게 움직이고 상호작용하도록 구현할 수 있다.

유니티의 물리 엔진은 주로 NVIDIA의 PhysX 물리 엔진을 기반으로 작동한다.     
다음은 유니티의 물리 엔진 작동 원리에 대한 간단한 설명이다:

1. 물리 업데이트 주기: 유니티의 물리 엔진은 일정한 시간 간격으로 물리적인 시뮬레이션을 실행한다.    
이를 물리 업데이트 주기(Physics Update Rate)라고 한다.  
기본적으로 프레임 속도(Fixed Timestamp)에 따라 물리 업데이트 주기가 결정되지만, 개발자들은 설정을 조정하여 원하는 물리 업데이트 주기를 지정할 수도 있다.
2. 충돌 검사: 물리 엔진은 각 게임 오브젝트의 콜라이더(Collider) 컴포넌트를 통해 충돌 검사를 수행한다.   
충돌 검사는 물체들 간의 겹침 여부를 확인하여 충돌이 발생했는지 감지한다.
3. 물리 시뮬레이션: 충돌이 발생하면 물리 엔진은 해당 게임 오브젝트의 질량, 속력, 힘 등 물리적인 특성을 고려하여 물체의 움직임을 시뮬레이션한다.     
이러한 시뮬레이션은 게임 오브젝트에 부착된 리지드바디(Rigidbody) 컴포넌트를 통해 제어된다.
4. 중력 적용: 물리 엔진은 중력을 모방하여 물체들에게 아래 방향으로 힘을 가한다.     
이로 인해 물체들이 떨어지는 동작을 구현할 수 있다.
5. 물체 상호작용: 물리 엔진은 물체들 간의 상호작용을 처리한다.  
충돌한 물체들이 서로에게 힘을 가하고, 관성에 따라 움직임이 전달되는 등의 상호작용이 이루어진다.
6. 물리 엔진 레이어: 물리 엔진은 물리적인 계산을 레이어별로 관리한다.   
이를 통해 어떤 물체들은 충돌하지 않거나, 충돌이 무시되어야 하는 경우를 설정할 수 있다.

유니티의 물리 엔진은 게임 오브젝트들이 현실적인 물리적 동작을 수행하도록 돕는다.

# 2.7. 네트워킹
유니티 엔진은 네트워킹(Networking)을 통해 다중 플레이어 게임을 구현할 수 있는 기능을 제공한다.  
네트워킹은 여러 플레이어가 동시에 게임 세계에 접속하여 상호작용할 수 있도록 해주는 기술로, 멀티플레이어 게임을 가능하게 한다.   
유니티 엔진의 네트워킹 작동 원리는 아래와 같은 단계로 이루어진다:

1. 네트워크 설정: 먼저, 개발자는 프로젝트의 네트워크 설정을 구성해야 한다.  
유니티 에디터에서 플레이어 수, 호스트와 클라이언트 설정, 서버 접속 등의 네트워크 옵션을 설정한다.
2. 네트워크 컴포넌트 추가: 각각의 게임 오브젝트는 네트워크 컴포넌트를 추가해야 한다.    
네트워크 컴포넌트는 게임 오브젝트를 네트워크로 동기화하여 다른 플레이어들과 동일한 사앹를 유지할 수 있게 한다.
3. 네트워크 식별자 설정: 각 게임 오브젝트는 고유한 네트워크 식별자를 가져야 한다.   
이 식별자는 게임 오브젝트가 네트워크에서 구분되는 역할을 한다.  
일반적으로 네트워크 식별자는 네트워크 뷰(NetworkView) 컴포넌트를 통해 설정된다.
4. 호스트 및 클라이언트 접속: 게임 플레이어들은 호스트 또는 클라이언트로 게임에 접속한다.   
호스트는 게임 세계를 호스팅하고, 클라이언트는 호스트와 연결하여 게임에 참여한다.
5. 데이터 동기화: 네트워크로 연결된 게임 플레이어들은 네트워크 컴포넌트를 통해 게임 오브젝트의 상태를 주기적으로 동기화한다.    
이로 인해 모든 플레이어들은 동일한 게임 세계를 볼 수 있게 된다.
6. RPC(Remote Procedure Call): RPC는 네트워크 플레이어들 간에 함수를 호출하는 기능을 제공한다.  
네트워크 상에서 함수를 호출하여 게임 오브젝트들 간에 상호작용을 구현할 수 있다.
7. 랭킹 및 매칭: 네트워킹은 랭킹 시스템과 매칭 시스템을 구현하는 데에도 사용된다.   
이를 통해 플레이어들끼리 경쟁하고, 적절한 상대와 매칭되어 게임을 즐길 수 있다.

이러한 네트워킹 기능을 통해 유니티 엔진은 다중 플레이어 게임을 구현할 수 있게 되며, 인터넷을 통해 플레이어들이 함께 플레이하거나 경쟁할 수 있도록 지원한다.

# 3. 유니티 생명주기
유니티 엔진은 다양한 생명주기(Lifecycle) 단계를 가지고 있으며, 이러한 단계들은 게임 오브젝트와 스크립트 등이 어떻게 동작하는지를 관리하고 제어하는 데에 사용된다.   
유니티 엔진의 주요 생명주기 단계는 다음과 같다:

1. 초기화(Initialization):  
    * Awake(): 게임 오브젝트가 생성되면 가장 먼저 Awake() 함수가 호출된다.  
    이 단계에서는 컴포넌트의 초기화를 수행한다.     
    즉, 변수를 설정하거나 다른 컴포넌트와의 연결을 설정하는 등의 작업이 이루어진다.
2. 활성화(Active):
    * OnEnable(): Awake() 함수가 호출된 다음에 OnEnable() 함수가 호출된다.  
    이 단계에서는 게임 오브젝트가 활성화되었을 때 필요한 초기화를 수행한다.     
    보통 이 단계에서 이벤트 리스너 등을 등록한다.
3. 업데이트(Update):
    * Update(): 게임 오브젝트가 활성화된 동안에는 프레임마다 Update() 함수가 호출된다.  
    이 단계에서는 게임 오브젝트의 상태를 업데이트하고 게임 로직을 실행한다.
4. 물리 업데이트(Physics Update):
    * FixedUpdate(): 프레임 속도(Fixed Timestep)에 따라 물리 엔진 업데이트 주기에 맞추어 FixedUpdate() 함수가 호출된다.     
    이 단계에서는 물리 연산을 처리한다.     
    물리적인 움직임과 상호작용은 이 단계에서 다룬다.
5. 렌더링(Rendering):
    * LateUpdate(): 모든 업데이트가 끝난 후 LateUpdate() 함수가 호출된다.   
    이 단계에서는 주로 카메라의 움직임이나 다른 오브젝트들의 위치 조정 등을 수행한다.   
    이렇게 함으로써 업데이트 이후에 다른 오브젝트들의 상태를 바탕으로 움직임을 조정할 수 있다.
6. 비활성화(Inactive):
    * OnDisable(): 게임 오브젝트가 비활성화되거나 더 이상 사용되지 않을 때 OnDisable() 함수가 호출된다.     
    이 단계에서는 활성화 시에 등록한 이벤트 리스너 등을 해제한다.
7. 제거(Destroy):
    * OnDestroy(): 게임 오브젝트가 제거될 때 OnDestroy() 함수가 호출된다.   
    이 단계에서는 필요한 정리 작업을 수행한다.

이러한 생명주기 단계들을 이해하고 활용하면 게임 오브젝트와 스크립트의 동작을 더욱 효율적으로 제어하고 관리할 수 있다.   
게임 오브젝트와 스크립트의 생명주기를 올바르게 다루면 메모리 누수나 예상치 못한 동작 등을 방지할 수 있다.

![유니티 생명주기](/img/monobehaviour_flowchart.svg)

# 3.1. Awake vs Start
둘 다 클래스의 초기화에 사용되는 이벤트 함수로 호출 시기에 따른 차이가 있다.

* Awake
    * 스크립트와 연결된 게임 오브젝트가 인스턴스화 되거나 스크립트가 처음 로드될 때 호출된다
    * 해당 오브젝트가 Enable 상태가 아니라고 해도 위 조건에 따라 로드되면 호출된다
    * 다른 오브젝트에 대한 참조를 생성할 때 주로 사용하게 된다
        * 단 Awake 호출은 무작위
        * 무작위성으로 인해 다른 스크립트의 참조를 통해 접근하면 NullReferenceException 이 발생하게 된다
* Start
    * 해당 스크립트 컴포넌트가 활성화 되는 순간 호출된다
    * 호출 시기는 Awake 보다는 느리게 첫 Update보다는 빠르게 호출된다
    * Start에서는 참조를 통해 접근하는 작업이 가능하다

### OnEnable vs Start
둘 다 '컴포넌트가 활성화 될 때' 불린다는 공통점이 있어 묶이게 되지만 Start는 한 번, OnEnable은 활성화 될 때 마다 불리게 된다는 차이점이 있다.   
때문에 초기화 작업에 OnEnable을 활용하면 안된다.    
OnEnable은 주로 오브젝트 풀링에 사용하게 되는 함수라고 볼 수 있다.

# 3.2. Update vs FixedUpdate vs LateUpdate
* Update: 프레임 단위로 호출됨
* LateUpdate: Update 호출 뒤 호출됨
* FixedUpdate: 고정 단위로 호출됨

FixedUpdate의 '고정 단위'는 물리 엔진에 의해 결정 되어 컴퓨터 성능에 따라 프레임이 다르게 나와 호출 간격이 일정하지 않은 Update와는 달리 일정하게 불리게 된다.   
이런 이유로 인해서 Rigidbody를 조작할 때는 FixedUpdate를 사용하게 된다.

# 4. C# & Unity
# 4.1. 박싱 & 언박싱
* 값 타입
    * C#에서 구조체, 열거 타입 등은 값 타입이다
    * System.ValueType 로부터 항상 상속
    * 스레드 스택에 할당이 된다.
* 참조 타입
    * C#에서 모든 클래스는 참조 타입이 된다.    
    * System.Object로부터 상속
    * 힙에 저장이 되며 GC가 관리하게 된다.
        * 이 힙 메모리의 주소를 가리키는 값은 스택에 저장이 된다.

박싱과 언박싱의 차이:

* 박싱: 값 타입을 참조 타입으로 변경
* 언박싱: 참조 타입을 값 타입으로 변경

이며 이 둘의 작업은 기본 작업들에 비해 비용이 크기 때문에 가급적 사용하지 않는게 좋다.  
다시 박싱, 언박싱하는 과정을 통해서 힙에 가비지가 쌓여 GC에 무리를 줄 수 있는 작업이기 때문이다.

이를 해결하기 위해서는 가급적 제네릭을 활용해 줘야 한다.

# 4.2. 직렬화 & 역직렬화
### 정의
직렬화는 특정 객체를 바이트 단위로 변경한 뒤 디스크에 저장하거나 네트워크로 보낼 수 있게 만들어주는 것이다.     
역직렬화는 직렬화된 바이트 배열을 원래 객체로 변경하는 과정을 의미한다.

### 직렬화 이유
직렬화는 현재 사용하고 있는 데이터에 대해서 영속성을 부여하기 위함이다.     
영속성은 프로그램을 종료하더라도 사라지지 않는 특성을 의미한다.

이런 식으로 프로그램 종료 후에도 객체에 관한 정보를 남겨두고 싶을 때 직렬화를 사용하게 된다.    
주로 플레이어의 데이터들이 이에 속하게 된다.

### 유니티에서 직렬화가 되는 것들
모든 요소들이 직렬화 되어 저장할 수 있는 상태가 되는 건 아니다.     
또한 유니티의 경우에는 다른 언어들과는 살짝 다르게 동작할 수 있으니 아래 내용을 알아두어야 한다.

* public이거나 [SerializeField] 속성이 있어야 한다
* static, const, readonly가 아니어야 한다
* 직렬화 할 수 있는 필드 타입이 있어야 한다     
=> 직렬화 할 수 있는 필드 타입은 아래와 같다    
    * [Serializable] 속성이 있는 비추상, 비일반 커스텀 클래스
    * [Serializable] 속성이 있는 커스텀 구조체
    * UnityEngine.Object 에서 파생된 오브젝트에 대한 참조
    * int, double, bool 같은 기본 데이터 형식
    * 열거형 타입
    * Vector2, Vector3, Color 등과 같은 특정 Unity 내장 타입

# 4.3. const vs readonly
C++과 다르게 C#에서는 readonly 가 있어 수정이 안되는 읽기 전용 키워드를 제공하고 있다.  
이 둘의 차이를 간단하게 정리하면 아래와 같다:

* const
    * 컴파일 타임 상수 (컴파일 시 변수가 값으로 대체)
    * 스택에 위치하게 된다
    * 선언과 동시에 값을 할당
    * 내장 자료형에만 사용 가능
        * 때문에 사용자 정의 클래스로는 불가능
* readonly
    * 런타임 상수 (런타임에 상수에 대한 참조)
    * 힙에 위치하게 된다
    * 생성자에서 초기화 가능 (그 외 변경 불가능)
    * 어떤 타입과도 사용 가능

### const 보다는 readonly가 좋다
둘 중 가장 큰 차이는 readonly는 상수에 대한 참조 코드를 생성한다는 점이다.  
때문에 const의 값을 변경하게 된다면 이를 사용하는 곳은 전부 재컴파일을 해야 한다.   
만일 재컴파일 하지 않으면 이전의 const 값으로 되어 있어 문제가 될 수 있다.  
다만 readonly의 경우에는 일부만 리빌드 해도 이를 사용하는 다른 코드들은 참조를 가지고 있으므로 리빌드 없이 올바르게 사용이 가능하다.

그 외 const는 스택에 있어 빠르다는 장점을 가지고 있지만 그 외의 유연성이 떨어지기에 아래 경우들을 제외하고 가급적 readonly를 사용하는게 좋다.

* 특성의 매개변수
* switch/case 문의 레이블
* enum 정의

# 4.4. string
C#에서의 string은 immutable(불변) 속성을 가지고 있다.   
string이 이렇게 불변속성이 된 이유는 멀티스레드 환경을 고려해 여러 스레드들이 엑세스 할 때 이들에 대한 동기화 처리를 하는 것보다 변경이 안되게 읽기 전용으로 만드는게 값이 더 싸다고 생각한 것이다.

때문에 string에 대한 조작(+=, -= 등)을 하게 되면 이전의 객체에서 복사 후 연산을 한 뒤 이를 대입해주므로 이전의 객체는 가비지가 되어 이후 GC의 처리를 받게 된다.     
때문에 수정이 많이 일어나는 문자열로 예상이 된다면 StringBuilder 등의 클래스를 사용하는게 좋다.

### StringBuilder가 string 보다 수정에 용이한 이유
StringBuilder는 기본적으로 16문자를 담을 수 있는 자리를 잡는다.     
이렇게 할당 된 크기 내에서는 어떠한 수정을 해도 가비지가 생성되지 않는다.

만일 미리 할당한 버퍼가 다 찬 상태에서 append를 하게 되면 새 버퍼를 할당한 뒤 버퍼간 링크를 구성한다고 한다.

# 4.5. Garbage Collector
C#과 C++의 대표적인 차이가 GC의 유무다.

일단 C#, 즉 .Net의 GC는 Mark and Sweep 알고리즘을 사용하고 있다.    
이를 간단하게 설명하면 아래와 같다:

* 전역 변수, 현재 함수의 로컬 변수 등을 Root로 잡게 된다
* 이 Root를 기반으로 점점 참조를 타고 다니면서 방문한 것들을 Mark 해준다
* 이러한 Mark 작업이 끝나게 된다면 이후 Sweep 단계로 진입한다
* Sweep 단계에서는 Mark 되지 않은 것들을 가비지로 판단해 처리하게 된다

이런 작업을 거쳐 GC가 동작을 하게 된다.

### .Net과 Unity의 GC
일단 내부적으로 GC의 알고리즘은 Mark and Sweep 을 기반으로 하게 되는데 그 이후의 과정이 다르게 된다.

.Net에서는 0~2세대까지 총 3개의 세대를 통해서 관리를 하게 된다.

유니티에서는 Boehm-Demers-Weiser 라는 알고리즘을 통해 GC 작업을 하게 된다.  
Mark and Sweep 인것은 같으나 세대 구분이 없고 메모리 정렬도 없다.   
때문에 19 버전 이상에서 제공하게 되는 점진적 GC 작업을 활용하거나 오브젝트 풀링 등의 기법을 활용해서 최대한 최적화를 해줘야 할 필요가 있다.

### 상호 참조 해결법
만일 두 객체가 서로 참조중이라 하더라도 외부에서 참조가 없어 Mark 되지 않는다면 Sweep 단계에서 해체된다.

# 4.6. delegate & event
### delegate
C# 에서 델리게이트는 함수를 타입화 한 것이다.    
파라미터와 리턴 타입을 통해 정의하게 되며 이후 리턴, 파라미터 타입이 같은 메서드들과 호환되어 이 메서드들에 대한 참조를 가질 수 있게 된다.

```c#
public delegate void VoidAndIntEx(int i);

public class ExampleClass
{
    public void DoSomething(VoidAndIntEx exFunc)
    {
        // 인자로 받은 함수를 호출한다
        exFunc(1);
    }
}
```

C#에서 이런 델리게이트를 활용해 메서드를 담아두는 역할을 하거나 함수 인자로 넘겨 콜백 패턴을 구현하는 등 다양한 곳에 사용하게 된다.

### event
이벤트는 결과적으로 델리게이트와 비슷한 일을 하게 되지만 한 가지 큰 차이점은 이벤트를 호출 할 수 있는건 해당 이벤트를 가진 클래스만 가능하다는 것이다.

```c#
class ExampleClass
{
    public event Action ExampleEvent;

    // ...
    if(ExampleEvent != null)
    {
        ExampleEvent();
    }
}
```

### Action, Func, Predicate
이 키워드들은 자주 사용하게 되는 델리게이트를 템플릿화 한 것들이다.

* Action
    * 함수 파라미터가 T 이고 반환값이 void 인 경우
* Func<T, TResult>
    * 함수 파라미터가 T 이고 반환값이 TResult 인 경우
* Predicate
    * 함수 파라미터가 T 이고 반환값이 bool 인 경우

### null 조건부 연산
델리게이트나 이벤트를 다루다 보면 null인지 체크를 해줘야 한다.  
만일 null인 델리게이트를 호출한다면 NullReferenceException이 발생하게 된다.

```c#
if(ExampleEvent != null) {
    ExampleEvent();
}
```

위 코드에서 문제점은 2가지 있다.

* 멀티스레드에서 호출할 경우의 문제
* 코드가 길어짐

멀티스레드에서 문제는 복잡하게 된다.    

```c#
if(ExampleEvent != null) // 여기선 문제가 생기지 않으나
{
    // 여기서 다른 스레드가 구독을 취소해서 null이 된다
    ExampleEvent(); // NullReferenceException
}
```

이런 복잡한 문제는 검출이 어렵기에 아래 '복사 후 실행' 이란 방법을 통해서 예방할 수 있다.

```c#
var CopiedEvent = ExampleEvent;

if(CopiedEvent != null)
{
    // 여기서 ExampleEvent 구독 취소 해도 문제 생기지 않음
    CopiedEvent();
}
```

다만 이 경우 위에 언급한 '코드가 길어진다'는 문제는 해결하지 못한다.    
매번 복사하는 것도 좋은 방안은 아니다.

때문에 ?. 연산자를 활용한다.    
?. 연산자는 ? 왼쪽의 항이 null이 아니라면 . 뒷부분을 실행하겠다는 의미의 연산자이다.

```c#
ExampleEvent?.Invoke();
```

함수의 경우 Invoke 를 붙여서 호출할 수 있게 된다.   
그리고 이 연산자의 경우 원자적으로 수행이 되는 연산자라서 이 연산 도중 다른 스레드가 개입할 여지가 없어 멀티 스레드 환경에서도 안전하게 작동하게 된다.

# 4.7. this
### 클래스의 현재 인스턴스 this
흔히 다른 언어에서도 지원하는 것으로 클래스의 현재 인스턴스를 가리키는 키워드이다.  
매개변수 이름과 클래스 필드가 이름이 같다면 this로 구분할 수 있게 된다.

클래스 내에서 클래스 필드를 사용할 때는 다 this가 생략된 경우라고 볼 수 있다.

### 생성자 this()
생성자의 이름은 클래스 이름과 동일해야 하며 void 형식이어야 한다.

```c#
class MyClass
{
    int a;
    int b;

    public MyClass()
    {
        a = 10;
    }

    public MyClass(int b)
    {
        a = 10;
        this.b = b;
    }
}
```

다만 이 경우 너무 중복되는 코드들이 양산될 수 있어서 this() 생성자를 사용하는 것이다.   
this()는 자기 자신의 생성자를 가리키며 이는 생성자에서만 활용이 가능하다.

```c#
class MyClass
{
    int a;
    int b;

    public MyClass()
    {
        a = 10;
    }

    public MyClass(int b) : this()
    {
        this.b = b;
    }
}
```

this() 키워드는 생성자를 가리키기에 인자를 줘서 인자를 받는 다른 생성자를 가리킬 수도 있다.

### 정적 함수 파라미터의 this
```c#
public static void Shuffle<T>(this IList<T> list)
```

정적 함수 파라미터에 사용하는 this는 확장 메서드를 만드는데 사용되는 키워드이다.    
이를 활용하면 멤버 함수를 호출하듯 함수를 호출할 수 있게 된다.

```c#
List<MyClass> exList = new List<MyClass>();
// ...
Shuffle(exList); // 이렇게도 가능하고
exList.Shuffle(); // 이렇게도 가능하다, this 파라미터 덕분에
```

이런 식으로 클래스나 인터페이스를 확장할 수 있게 된다.

다만 기존 클래스의 함수와 동일한 시그니처로 정의하면 호출되지 않게 된다.    
이 이유는 확장 메서드는 컴파일 타임에 바인딩이 되는데 컴파일러가 함수 호출을 볼 때 인스턴스 함수를 먼저 보게 되고 그 다음 확장 메서드를 보게 된다.  
때문에 확장 메서드가 우선순위에서 밀려 호출되지 않게 되는 것이다.

# 4.8. List, Dictionary 등 자료구조의 내부
### 내부 자료구조
|컨테이너|자료구조|
|---|---|
|List<>|배열|
|SortedSet<>|레드-블랙 트리|
|HashSet<>|해시 테이블|
|Dictionary<,>|해시 테이블|
|SortedList<,>|배열|
|SortedDictionary<,>|레드-블랙 트리|

### List vs vector
List는 C++의 vector와 유사하게 동작하며 메모리에는 배열처럼 올라가게 된다.  
또한 원소 삽입이 있을 때 List의 용량을 초과하게 되면 새 공간을 할당해 기존 원소들을 복사해 가기에 최대 O(N) 시간 복잡도를 가지게 될 수도 있다.

(Remove의 경우 따로 용량 변화가 없다)

### SortedSet = set, HashSet = unordered_set
내부적으로 레드-블랙 트리를 사용하는 자료구조들의 경우 정렬된 완전 이진트리 이므로 삽입, 삭제에 있어서 O(logN) 시간이 소요되며 해시를 사용하는 자료구조들은 대부분 O(1)이지만 최악의 경우 O(N)이 될 수 있음을 알아야 한다.

### Dictionary vs SortedDictionary
대부분의 경우에서 성능은 Dictionary가 더 뛰어나다.  
삽입에는 Dictionary가 약 3배 빠를 수 있고, 검색에는 아주 근소한 차이로 SortedDictionary가 빠를 수 있다.

때문에 항시 정렬된 상태로 데이터를 저장하는 것 외에는 Dictionary 사용이 더 좋다.

# 4.9. C# vs C++
### GC
C#의 GC는 Mark and Sweep 알고리즘에 기반을 두고 있으므로 힙에 할당된 객체에 대한 포인터 추적을 실행하게 된다.   
이로 인해서 C++의 생성-소멸 주기보다는 오버헤드가 걸린다.   
그리고 수많은 객체들을 생성한 후 나중에 GC를 돌리게 되면 더 많은 시간을 사용하게 되므로 속도가 더 느려지게 된다.

C#은 세대 기반 알고리즘을 도입해 '살아 있을 가능성이 있는 객체'를 뒤로 물러나게 해 GC 시간을 줄이는 등의 노력을 하고 있다.  

### 가상 머신
'VM을 사용하면 느리다'라는 말이 나오는 주된 이유는 초기 구동시에 JIT 컴파일러를 위해 한번 대기하는 과정이 있어서 라고 한다.     
다만 이 경우 한번 실행이 되면 이후에는 여러번 사용할 수 있기에 이에 대한 오버헤드를 잘 살펴봐야 한다.

일단 C++로 작성된 프로그램은 대부분 32비트 코드로 컴파일이 되며 64비트 프로세서에서도 32비트로 돌아가게 된다.   
JIT를 사용하는 C#의 경우 타겟 플랫폼에 대한 이해도를 가질 수 있어서 64비트에 맞춰 컴파일을 한다.    
떄문에 이런 부분에 있어서 장점을 가질 수도 있다.

# 5. 로컬 좌표 & 월드 좌표
유니티에서의 로컬 좌표와 월드 좌표는 게임 오브젝트의 위치와 회전을 다루는 데 사용되는 개념이다.     

1. 로컬 좌표(Local Coordinates):    
로컬 좌표는 게임 오브젝트 자체의 지역 좌표 시스템을 나타낸다.   
각 게임 오브젝트는 자신만의 로컬 좌표 시스템을 가지며, 이를 기준으로 해당 오브젝트의 위치, 회전 및 크기를 정의한다.     
로컬 좌표 시스템의 원점은 게임 오브젝트의 중심이다.     
즉, 오브젝트의 위치는 이 로컬 좌표 시스템 내애서 상대적으로 표현된다.   
로컬 변환(이동, 회전, 크기 조절)은 해당 오브젝트 자체에만 영향을 미치며, 다른 오브젝트에 영향을 주지 않는다.
2. 월드 좌표(World Coordinates):    
월드 좌표는 게임 세계 전체의 전역 좌표 시스템을 의미한다.   
모든 게임 오브젝트는 월드 좌표 시스템 내에서 위치하며, 이 좌표 시스템은 모든 오브젝트 간의 절대적인 위치와 상대적인 위치를 나타낸다.    
오브젝트의 월드 좌표는 게임 세계 안에서의 실제 위치를 나타낸다.     
다른 오브젝트와의 상호작용, 충돌 검사 및 위치 계산은 주로 월드 좌표를 기반으로 수행된다.

로컬 좌표와 월드 좌표 간의 변환은 오브젝트의 계층 구조와 부모-자식 관계에 의해 결정된다.    
부모 오브젝트의 변환은 자식 오브젝트에 영향을 미친다.   
즉, 부모 오브젝트의 로컬 변환은 자식 오브젝트의 월드 좌표에 영향을 준다.

유니티에서는 'Transform' 컴포넌트를 사용하여 오브젝트의 로컬 및 월드 변환 정보를 관리하고 조작할 수 있다.   
이를 통해 오브젝트의 위치, 회전 및 크기를 다루며, 게임 내에서 상호작용과 위치 계산을 용이하게 할 수 있다.

# 5.1. 로컬 회전 & 월드 회전
1. 로컬 회전(Local Rotation):   
로컬 회전은 게임 오브젝트의 자체적인 회전 변환을 나타낸다.      
각 게임 오브젝트는 자신만의 로컬 좌표 시스템을 가지며, 이 좌표 시스템을 기준으로 회전이 적용된다.   
오브젝트의 로컬 회전을 변경하면 해당 오브젝트의 모양이 회전하게 된다.   
로컬 회전은 해당 오브젝트만을 기준으로 적용되며, 다른 오브젝트에 영향을 주지 않는다.
2. 월드 회전(World Rotation):   
월드 회전은 게임 세계 전체의 좌표 시스템을 기준으로 한 회전 변환을 의미한다.    
오브젝트의 월드 회전을 변경하면 해당 오브젝트가 전체 게임 세계 내에서 회전하게 된다.    
월드 회전은 다른 오브젝트와의 상호작용, 충돌 감지, 위치 계산 등과 관련된 중요한 개념이다.

로컬 회전과 월드 회전 간의 차이점은 오브젝트의 부모-자식 계층 구조에 기인한다.      
부모 오브젝트의 로컬 회전이 변경되면, 자식 오브젝트의 로컬 회전에도 영향을 줄 수 있다.  
그에 반해 월드 회전은 게임 세계 전체에 적용되며, 부모 오브젝트의 변환과 상관없이 독립적으로 작동한다.

유니티에서 오브젝트의 로컬 및 월드 회전을 조작하려면 'Trasform' 컴포넌트의 'localRotation' 및 'rotation' 속성을 사용한다.   
로컬 회전은 오브젝트의 로컬 좌표 시스템을 기준으로 하며, 월드 회전은 게임 세계 전체를 기준으로 한다.    
이를 이용하여 오브젝트의 회전을 원하는 방식으로 조작할 수 있다.

# 6. 센터 & 피벗
유니티에서의 "센터(center)"와 "피벗(pivot)"은 게임 오브젝트의 위치와 회전을 조작할 때 중요한 개념이다.

1. 센터(Center):    
게임 오브젝트의 센터는 해당 오브젝트의 로컬 좌표 시스템에서의 중심 지점을 의미한다.     
이것은 오브젝트가 어디에 위치하는지를 나타내며, 오브젝트의 로컬 공간 내에서 중심점으로 간주된다.    
예를 들어, 큐브 오브젝트의 센터는 큐브의 중심으로 간주된다.     
센터를 기준으로 오브젝트의 위치가 결정된다.
2. 피벗(Pivot):     
게임 오브젝트의 피벗은 해당 오브젝트를 회전할 때 중심이 되는 지점이다.      
피벗은 오브젝트의 로컬 좌표 시스템 내에서 설정되며, 오브젝트의 회전 중심을 정의한다.    
회전 시에 피벗은 오브젝트 주위를 중심으로 회전하게 되며, 오브젝트의 로컬 공간 내에서만 영향을 미친다.   
피벗을 변경하면 오브젝트의 회전 동작이 변경될 수 있다.

유니티에서는 오브젝트의 센터와 피벗을 조작할 수 있는 방법이 있다.   
일반적으로는 오브젝트를 생성할 때 기본적으로 센터와 피벗이 정의되며, 이후에도 편집할 수 있다.   
센터와 피벗을 조작하면 오브젝트의 위치와 회전 동작을 원하는 대로 조절할 수 있다.    
이것은 모델의 정렬, 애니메이션, 게임 플레이 등에 활용될 수 있다.

오브젝트의 센터와 피벗을 조작하려면 유니티의 에디터 내에서 해당 오브젝트를 선택한 후 'Transform' 컴포넌트의 인스펙터에서 'Position'과 'Rotation' 값을 조정하면 된다.    
또한 몇몇 경우에는 별도의 툴이나 스크립트를 사용하여 센터와 피벗을 조작하는 것이 유용할 수 있다.

# 7. 기즈모
유니티의 "기즈모(Gizmo)"는 에디터 상에서 시각적으로 오브젝트의 위치, 회전, 크기 등을 보여주고 조작할 수 있는 도구 및 표시 요소를 말한다.    
기즈모는 게임 개발자가 에디터 내에서 씬(Scene)을 구성하고 조작하는 데 도움을 주는 중요한 기능 중 하나이다.

기즈모는 다양한 유형의 오브젝트와 관련하여 나타날 수 있으며, 주로 다음과 같은 목적으로 사용된다:

1. 트랜스폼 조작: 기즈모를 사용하여 선택한 게임 오브젝트의 위치, 회전 및 크기를 조작할 수 있다.     
에디터 내에서 직접 조작하거나, 값을 입력하여 오브젝트의 변환 정보를 수정할 수 있다.
2. 충돌 검사 및 위치 조정: 기즈모를 사용하여 충돌 검사를 수행하거나 오브젝트를 정확한 위치로 이동시킬 수 있다.      
이를 통해 게임 오브젝트 간의 상호작용을 시각적으로 확인하고 조정할 수 있다.
3. 애니메이션 및 경로: 기즈모를 사용하여 애니메이션 및 경로의 편집을 수행할 수 있다.    
이를 통해 애니메이션의 키 프레임을 조작하거나, 경로를 시각적으로 수정할 수 있다.
4. 씬 구성: 기즈모를 사용하여 씬 내의 오브젝트들을 배치하고 정렬할 수 있다.     
예를 들어, 오브젝트 간의 거리나 간격을 정확하게 조절할 때 사용할 수 있다.

유니티는 다양한 기본 기즈모를 제공하며, 개발자는 이를 확장하거나 사용자 정의하여 자신의 요구에 맞게 사용할 수 있다.     
기즈모를 활용하여 오브젝트의 변환 정보를 직접 조작하거나 시각적으로 확인함으로써 게임의 개발 및 디버깅 프로세스를 더욱 효율적으로 수행할 수 있다.

# 8. 회전
유니티에서 회전은 게임 오브젝트의를 중심으로 축을 기준으로 회전 변환을 적용하는 것을 의미한다.      
회전은 오브젝트의 방향이나 모양을 변경하는 데 사용된다.     
유니티에서 회전은 오브젝트의 'Transform' 컴포넌트를 통해 조작할 수 있다.

회전은 주로 세 가지 요소로 정의된다:

1. 오일러 각(Euler Angles):     
오일러 각은 X, Y, Z 축 주위의 회전을 나타내는 값으로, 각 축의 회전을 독립적으로 지정할 수 있다.     
그러나 오일러 각은 "짐벌 락(Gimbal Lock)"이라는 문제를 가지고 있어 복잡한 회전 동작에 사용하기에는 제한이 있을 수 있다.
2. 쿼터니언(Quaternion):    
쿼터니언은 회전을 나타내는 더 강력하고 안정적인 표현 방식이다.      
유니티에서는 주로 쿼터니언을 사용하여 회전을 표현하며, 회전 연산을 수행할 때 좀 더 정확하고 예측 가능한 결과를 얻을 수 있다.
3. 회전 행렬(Rotation Matrix):      
회전 행렬은 3x3 행렬로, 회전 변환을 수행하는 데 사용된다.   
유니티는 내부적으로 회전 행렬을 사용하여 회전을 처리하지만, 일반적으로 직접 회전 행렬을 조작하는 경우는 드물다.

오브젝트의 회전은 주로 다음과 같은 용도로 활용된다:

- 방향 제어: 오브젝트의 회전을 조작하여 원하는 방향을 향하도록 만들 수 있다.    
주로 캐릭터나 카메라의 방향을 제어하는 데 사용된다.
- 애니메이션: 회전을 조작하여 애니메이션을 만들거나 조정할 수 있다.     
쿼터니언을 이용하면 부드럽고 정확한 회전 동작을 표현할 수 있다.
- 게임 오브젝트의 모양 변경: 오브젝트의 회전을 변경하여 모양을 바꾸거나, 물체를 기울이는 등 다양한 시각적 효과를 구현할 수 있다.

유니티에서 회전을 조작하려면 'Transform' 컴포넌트의 'rotation' 속성을 수정하면 된다.    
회전을 설정하거나 변경하면 오브젝트의 방향과 모양이 변화한다.   
또한 오브젝트의 부모-자식 관계나 로컬-월드 변환에 따라 회전이 영향을 받을 수 있다.

# 9. 이동
유니티에서의 이동은 게임 오브젝트를 움직이는 작업을 의미한다.   
이동은 게임 세계 내에서 오브젝트의 위치를 변경하는 것을 말하며, 주로 게임 캐릭터, 카메라, 아이템 등을 제어하거나 배치하는 데 사용된다.      
유니티에서 오브젝트의 이동은 'Transform' 컴포넌트를 통해 조작할 수 있다.

오브젝트의 이동은 크게 두 가지 방식으로 다루어진다:

1. 절대적인 이동(Absolute Movement):    
절대적인 이동은 원하는 위치로 오브젝트를 직접 이동시키는 것을 의미한다.     
이동하려는 목표 위치를 정확하게 지정하여 오브젝트를 이동시킨다.     
이동 후에는 오브젝트의 위치가 목표 위치로 설정된다.
2. 상대적인 이동(Relative Movement):    
상대적인 이동은 오브젝트의 현재 위치를 기준으로 상대적인 방향과 거리를 지정하여 이동시키는 것을 의미한다.   
현재 위치에서 상대적인 이동 값을 더하거나 빼서 새로운 위치를 계산하여 오브젝트를 이동시킨다.    

오브젝트의 이동은 다음과 같은 용도로 사용된다:

- 캐릭터 이동: 플레이어 캐릭터나 NPC를 이동시켜 게임 내에서 움직이는 동작을 구현한다.   
- 카메라 제어: 카메라를 이동시켜 다른 시점에서 게임을 관찰하거나 특정 위치를 초점으로 하는 등의 효과를 만든다.
- 아이템 배치: 아이템이나 물체를 원하는 위치에 배치하거나 이동시켜 게임 환경을 구성한다.
- 애니메이션: 이동을 사용하여 캐릭터의 걸음, 뛰기 등의 애니메이션을 만들거나 제어할 수 있다.

유니티에서 오브젝트의 이동은 'Transform' 컴포넌트의 'position' 속성을 조작하여 수행할 수 있다.      
이를 통해 절대적인 이동이나 상대적인 이동을 구현하고 오브젝트의 위치를 원하는 대로 조작할 수 있다.

# 10. 리지드 바디
유니티에서의 "Rigidbody"는 물리 엔진과 상호작용하여 게임 오브젝트에 물리적인 특성과 동작을 부여하는 컴포넌트이다.   
이 컴포넌트를 사용하면 게임 오브젝트가 중력, 충돌, 운동 등의 물리적 현상에 따라 움직이거나 상호작용할 수 있다.

Rigidbody는 주로 물리 시뮬레이션을 통해 오브젝트 간의 상호작용이나 환경과의 상호작용을 모델링하는 데 사용된다.      
일반적으로 물체가 중력에 따라 떨어지거나, 충돌 시 힘을 받아 움직이거나 튀어오르는 등의 동작을 구현할 때 유용하다.

Rigidbody의 주요 속성과 기능은 다음과 같다:

1. 질량(Mass): 물체의 질량을 나타낸다.      
질량이 큰 물체는 중력에 더 많이 영향을 받으며, 충돌 시 힘을 더 받게 된다.
2. 중력(Gravity): 물체에 중력 효과를 적용할지 여부를 결정한다.  
중력을 켜면 물체는 아래로 떨어지게 된다.    
3. 운동(Forces): 힘 또는 속도를 적용하여 물체를 움직이거나 회전시킬 수 있다.    
'AddForce'나 'AddTorque' 메서드를 사용하여 힘을 추가할 수 있다.
4. 물리 충돌(Collision): Rigidbody를 가진 물체는 다른 Collider와 충돌할 때 물리적인 효과를 받는다.  
충돌을 통해 움지깅거나 튀어오르는 등의 동작이 발생할 수 있다.
5. 중력 조정(Gravity Scale): 중력 효과를 물체 별로 조정할 수 있다.      
이를 통해 다양한 물리적 동작을 만들 수 있다.

유니티에서 Rigidbody 컴포넌트는 주로 3D 물리 시뮬레이션에서 사용되며, 2D 게임에서는 'Rigidbody2D' 컴포넌트가 사용된다.  
Rigidbody를 사용하려면 게임 오브젝트에 해당 컴포넌트를 추가하고, 필요한 속성 및 메서드를 활용하여 물리적 동작을 구현하면 된다.

# 11. 콜라이더
유니티에서의 "Collider"는 게임 오브젝트가 다른 오브젝트와 상호작용하고 충돌을 감지할 수 있도록 도와주는 컴포넌트이다.   
콜라이더는 주로 물리 시뮬레이션과 충돌 감지에 사용되며, 게임 환경에서 오브젝트 간의 상호작용을 모델링하는 데 중요한 역할을 한다.

콜라이더는 게임 오브젝트의 형태를 정의하고 다른 오브젝트와의 경계를 나타내며, 주변 오브젝트와 상호작용할 때 물리적 동작이나 충돌 검사를 수행한다.   
콜라이더를 사용하여 오브젝트 간의 충돌이나 상호작용을 처리할 수 있다.

주요한 콜라이더 종류는 다음과 같다:

1. 박스 콜라이더(Box Collider): 박스 모양의 콜라이더로, 주로 상자 모양의 충돌 영역을 정의하는 데 사용된다.
2. 구 콜라이더(Sphere Collider): 구 모양의 콜라이더로, 주로 둥근 모양의 충돌 영역을 정의하는 데 사용된다.
3. 캡슐 콜라이더(Capsule Collider): 실린더 모양의 콜라이더로, 주로 원통 형태의 충돌 영역을 정의하는 데 사용된다.
4. 메쉬 콜라이더(Mesh Collider): 복잡한 형태의 콜라이더로, 3D 모델의 형태를 따라가며 충돌 영역을 정의하는 데 사용된다.
5. 터레인 콜라이더(Terrain Collider): 지형 모양의 콜라이더로, 지형 오브젝트의 지형 표면에 충돌 영역을 정의하는 데 사용된다.

콜라이더는 충돌 감지를 위해 사용되며, 오브젝트 간의 충돌이나 상호작용을 처리하려면 콜라이더를 가진 오브젝트 간의 상호작용을 처리하는 스크립트를 작성해야 한다.  
콜라이더와 Rigidbody 컴포넌트를 조합하여 오브젝트 간의 물리적 상호작용을 정밀하게 제어하고 게임의 리얼리즘을 높일 수 있다.

# 11. Lerp
유니티에서의 "Lerp"는 "선형 보간(Linear Interpolation)"을 의미하는 용어다.    
선형 보간은 두 지점 사이를 일정한 비율로 보간하여 새로운 값을 만들어내는 방법을 말한다.     
Lerp 함수는 시작 값과 끝 값 사이에서 선형 보간을 수행하며, 주로 애니메이션 및 값의 부드러운 변화를 구현하는 데 사용된다.

유니티의 'Mathf.Lerp' 함수나 'Vector3.Lerp', 'Quaternion.Lerp' 등의 메서드는 선형 보간을 사용하여 두 값 사이를 부드럽게 변화시키는 데 유용하다.     
이 함수들은 주로 두 가지 값 사이를 특정 비율로 보간하는 데 사용된다.

예를 들어, 두 위치 A와 B 사이를 t라는 비율로 보간하려고 할 때:
```c#
Vector3 interpolatedPosition = Vector3.Lerp(A, B, t);
```

여기서 't' 값은 0부터 1 사이의 값으로, 0에 가까울수록 결과 값은 A에 가까워지고, 1에 가까울수록 B에 가까워진다.      
't' 값을 조절하여 A와 B 사이를 원하는 비율로 부드럽게 이동하는 효과를 얻을 수 있다.

선형 보간은 애니메이션의 프레임 간 보간, 오브젝트의 이동 및 회전 애니메이션, 값의 부드러운 전환 등 다양한 상황에서 사용되며, 유니티의 애니메이션 및 게임 개발 프로세스에서 중요한 역할을 한다.