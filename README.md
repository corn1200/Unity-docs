# Unity-docs

# 목차

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