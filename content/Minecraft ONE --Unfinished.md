---
publish: true
---

# Minecraft: ONE

---

Minecraft: ONE은 현재 양분된 Minecraft의 생태계를 통합하는 목표를 지닌 가상의 신규 Minecraft 에디션이다.

ONE이라는 이름에는 총 두 가지의 각기 다른 뜻이 담겨있다. 첫 번째 뜻은 Minecraft의 공식적인 차원들인 Overworld, Nether, End를 나열한 역두문자어이다. 두 번째 뜻은 Microsoft가 자사 브랜드 명명에 주로 사용하는 단어 중 하나인 One의 연장선상이며, 이는 추가로 _하&#xB098;_&#xB85C; 통합한다는 Minecraft: ONE의 목표에 대응한다.

## 시스템

---

### 개발

---

Minecraft: ONE은 Unity로 대표되는 상용 엔진 대신 자체적으로 개발된 게임 엔진인 RenderDragon을 사용한다. 상용 엔진은 주로 폴리곤 기반의 메시를 사용하기에 복셀 기반 게임인 Minecraft에는 적합하지 않았다. RenderDragon은 Bedrock Edition에 적용되며 실사용 환경에서의 선례가 존재하는 엔진이다.

게임의 근본적인 실행 속도를 결정하는 그래픽 렌더링과 물리 엔진 등에는 Bedrock Edition과 동일하게 C++을 주요 코드 베이스로 사용한다. C++은 Java, C# 등과 달리 런타임이 없기에 일시적인 프리징을 유발하는 가비지 컬렉터가 포함되어 있지 않으며, 개발자가 메모리를 직접 조작하여 타 언어로는 어렵거나 번거로운 네이티브 최적화를 가능케 한다.

반면 대부분의 전체 코드 베이스가 C++로 작성된 Bedrock Edition과 달리, Minecraft: ONE은 인게임 콘텐츠 등의 상위 차원 로직에는 .NET 10 런타임 기반의 C#을 적용한다. 앞서 언급하였듯이 C++에 비하여 최적화 측면에서 부족한 면이 분명이 존재하는 C#이나, 이를 선택한 이유에는 크게 세 가지가 존재한다.

첫 번째 이유는 과거를 상회하는 C#의 완성도이다. 2011년 Bedrock Edition의 전신인 Pocket Edition의 개발 당시 C#은 .NET Framework라는 Windows에 종속된 전용 런타임에서만 구동되었으며, 실행 속도마저 현재에 비해 현저히 느린 언어였다. 이러한 점으로 인하여 운영체제가 다르고 PC에 비해 사양이 낮은 모바일 기기 구동을 지원해야 하는 Pocket Edition에는 적합하지 않았고, 결국 Bedrock Edition으로 이어지는 현재까지 C++이라는 양날의 검을 사용하게 된 사연이 존재한다.
그러나 10년이 넘는 세월이 흐른 현재, .NET Framework는 .NET Core를 거쳐 크로스 플랫폼을 지원하는 .NET으로 진화하였으며, C# 또한 JIT 컴파일러의 발전과 Native AOT의 지원, 저수준 메모리 제어 기능을 통해 Unity의 공식 언어가
