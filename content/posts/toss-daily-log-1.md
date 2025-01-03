+++
title = 'Toss Daily Log 1'
date = 2024-12-17T22:50:56+09:00
draft = false
tags = ['event']
+++

### 생각의 시작: 변화와 과정  

내가 생각했을때 이번 과정에서 가장 중요한 것은 **결과보다 과정**이다. 완벽한 기능을 추가하는 것 보다 주어진 환경에서 어떤 가치를 만들어낼 수 있는지를 보여주는 것이 핵심이라고 생각 한다. 이를 위해 앞으로 한 달간 나의 고민과 과정을 매일 기록하려 한다.  

---

### 도전 과제: 프로젝트의 현실  

현재 참여 중인 ~공공 프로젝트~는 레거시 시스템을 개선하는 프로젝트다. SI 프로젝트라 그런가 다음과 같은 형상을 띈다:  

1. **그대로 복제된 레거시 로직**  
   새로운 시스템은 기존 시스템의 로직을 거의 그대로 옮겨왔다. 결과적으로 **기술 부채**와 비효율성이 여전히 남아 있다. 이는 개선의 여지가 굉장히 많다는 점을 의미하기도 하지만 아래 기술 한 이유들로 인해 실제 개선으로 이어나가기에는 상당히 제한적이다. 상당히 복잡한 비즈니스 로직은 덤이다.

2. **제한된 개발 환경**  
   보안상의 이유로 **인터넷 접근이 제한**되어 있어 외부 자료를 활용하기 어렵다. 프로젝트는 굉장히 많은 업무들로 나누어져 있으며 각 업무는 타업무에서 활용할 수 있는 인터페이스를 제공한다. 인터페이스는 JAR파일로 제공되며 로컬 빌드는 상당히 무겁고 오래걸리며, 오류가 발생하기 쉬운 환경이다. 협업을 위해 깃을 사용하긴 하지만 제대로 활용하지는 않고, 코드 리뷰 또한 없다.
   이 프로젝트를 시작한지 2달정도 되어가는데, 온보딩 과정이나 문서화 (현행화) 된 개발자 환경 세팅이 거의 없다고 할 수 있었다.

3. **제한된 개발 일정**  
   프로젝트는 **막바지 단계**에 있어 대규모 수정이 불가능한 상황이다.  
   현재는 완성에 집중하는 시기이기 때문에 개선보다는 **유지**에 무게가 실려 있다. 오픈 전까지 매일 매일 결함이 올라오고, 해당 결함은 당일 빨리 쳐내는게 가장 중요한 업무이다. 

   이런 상황에서 나는 과연 어떤 것을 기여 할 수 있을까?

---

### 나의 접근법: 내가 겪은 어려움을 파해쳐보기

이런 제약 속에서도 **가치 있는 변화**를 만들어내기 위해 다음과 같이 접근하고자 한다:

1. **문제 분석**  
   사실 위 나열 한 문제점들과 바쁜 업무를 핑계 삼아, 이 시스템에 대해 깊이 파보려는 노력을 크게 안했다. 이 프로젝트의 인프라 구조에 대해서 이해하고 분석을 해보려는 시도를 안 한 상태에서 오래된 방식으로 치부한 것 같다. 
   
   이번 기회에 시스템을 꼼꼼히 분석하고 어떤 개선 점들이 있는지 생각해 봐야겠다.

2. **명확한 커뮤니케이션**  
   변화의 필요성과 해결 방안을 **데이터와 근거**로 명확히 전달하고, 나의 생각의 흐름을 논리적으로 설명한다.

3. **작은 변화부터 시작**  
   큰 구조 변경이 아닌 **로그 개선, 개발자 온보딩 프로세스 문서화** 등 작은 변화부터 시작한다.

---

### 결론: 과정이 가치를 만든다  

겉으로는 변화를 만들기 어려워 보이지만, 작은 개선과 관찰도 큰 의미를 가질 수 있다. 이 과정을 통해 바쁘다는 핑계로 미뤄놨던 전체적인 시스템을 더 깊이 이해하고, 프로젝트 온보딩을 하면서 절실하게 필요했던 (현행화된) 환경 세팅과 프로젝트 구조 문서화하는 부분부터 시작 할 수 있을 것 같다.