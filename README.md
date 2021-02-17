## summarize-structure
안드로이드 프로젝트 구조를 위해 사용한 라이브러리나 기본 지식을 정리합니다.

---------

### 리펙토링

현재 프로젝트는 Java(90%) + Kotlin(10%) 구성되어있다.

(1) Java + Kotlin을 유지하면서 사용할 경우 사용해야할 것

Dagger2, Retrofit3+OkHttp3, RxJava2

단점 : Dagger2와 RxJava2는 학습 곡선이 높다. 

(2) Kotiln 100%를 사용할 경우 사용해야할 것

Koin, Coruntine, LiveData, ViewModel
 
장점 : databinding 사용가능(livedata, viewmodel과 묶어 활용하면 더욱 더 효과 극대화)

단점 : 웬만한 코드는 전부 Kotlin으로 바꿔야한다.

---------

### 기초 지식

* **AAC(Android Architecture Components)**

안드로이드는 Activity, BroadcastReceiver, Service, ContentProvider 등 여러 컴포넌트들이 있고,
생명주기가 다르게 얽혀있습니다.
앱을 잘 만들기 위해서는 이러한 컴포넌트들을 부드럽게 연결해야 하는데,
생명주기를 학습하고 엉키지 않도록 고민하는 것은 결국 개발자의 몫이였습니다.
구글은 이 고민을 줄이기 위해 SDK에서 제공하는 컴포넌트들에 대해 개발자들에게 더 가이드를 주기를 원했습니다.
그래서 Android Architecture Components(AAC)를 만들었습니다.

여기서 중요한것은 

https://blog.kakaocdn.net/dn/b1WEWl/btqFK3PZ9oR/Zf0MW7IZfKT2d8bFZs3yX1/img.jpg

Clean Architecture란?

https://k-elon.tistory.com/38

Android Architecture Components를 활용하여 MVVM 적용하기

https://blog.gangnamunni.com/post/aac_mvvm/

안드로이드 공식 홈페이지 문서

https://developer.android.com/topic/libraries/architecture


* **MVC, MVP, MVVM**

MVC : View와 Model 사이의 의존도가 높아 유지보수가 어렵다.(비추천)

MVP : MVC와 달리 하는 일이 서로 분리 되었으나 View와 Presenter가 1:1 관계라서 밀접한 관계를 갖는다.(괜찮다고 생각함. 현재는 모르겠으나 배민도 mvp구조였었음)

MVVM : Data Binding을 이용하여 View와 View Model 사이의 의존성을 없앴다. (안드로이드에선 Good)

https://beomy.tistory.com/43


*  **비동기 프로그래밍**

비동기 프로그래밍을 쉽게 도와주는 라이브러리는 2가지가 있다.
이 라이브러리를 사용하여 주로 서버 api를 호출할때 사용한다.

Java-RxJava2 / Kotlin-Corountine(RxKotlin도 있으나 android에선 coroutine을 권장)

RxJava2와 Coroutine
https://thdev.tech/android/2019/11/30/RxJava-Corotuines-01/

Kotlin의 Coroutine
https://medium.com/hongbeomi-dev/coroutines-basic-e32053f18fdf

Rx 기초
https://k-elon.tistory.com/1

RxJava2 기초
https://taeiim.tistory.com/entry/RxJava2-2-Observable-Single-Maybe-%EB%9C%A8%EA%B1%B0%EC%9A%B4%EC%B0%A8%EA%B0%80%EC%9A%B4-Observable-%ED%8C%A9%ED%86%A0%EB%A6%AC%ED%95%A8%EC%88%98

RxJava2 책 추천
http://book.interpark.com/product/BookDisplay.do?_method=detail&sc.prdNo=269172314

*  **Retrofit2 + OkHttp3**

https://jongmin92.github.io/2018/01/29/Programming/android-retrofit2-okhttp3/

*  **Dagger2**

dagger2 기초

https://medium.com/@maryangmin/di-%EA%B8%B0%EB%B3%B8%EA%B0%9C%EB%85%90%EB%B6%80%ED%84%B0-%EC%82%AC%EC%9A%A9%EB%B2%95%EA%B9%8C%EC%A7%80-dagger2-%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-3332bb93b4b9

우아한 형제들의 기술 블로그

https://woowabros.github.io/experience/2019/07/31/android-dagger.html


*  **DataBinding**

안드로이드 공식 홈페이지 사용가이드

https://developer.android.com/topic/libraries/data-binding/?hl=ko

DataBinding 응용

https://superwony.tistory.com/43?category=735973


---------

### 참고자료

→ 참고할 프로젝트

[안드로이드 기본 제공만 사용하여 구조짜기]

https://github.com/dduddupark/assignment0608

[카카오커머스 과제 Kotlin + Corountin + Dagger2 + Retrofit2 + OkHttp3 + MVVM]

https://github.com/dduddupark/kakaoimage

[Dagger2 + Retrofit2 + OkHttp3 + RxJava + MVP 구조]

https://github.com/dduddupark/MVP

[Dagger2 + Retrofit2 + OkHttp3 + RxJava + MVVM 구조]

https://github.com/dduddupark/MvvmArchitecture

