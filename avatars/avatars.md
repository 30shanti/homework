## 5월 첫째주 과제 
#### Float, Flex 활용하기
- float를 이용해 아래의 이미지처럼 만들기
![float](/images/Avatars_(1).png)


- flex를 이용해 아래의 이미지처럼 만들기
![flex](/images/Avatars_(2).png)


#### Float 활용하기
##### -HTML

1. 이미지와 상태확인용 동그라미 생성을 위한 요소를 클래스 이름user로 지정한 div 요소 안에 묶고 총 8개의 요소를 생성
2. div 요소를 동그라미로 만들려고 클래스 이름을 status로 지정, 이때 접근성을 높이기 위해 label로 온라인/오프라인을 적어둠
3. 위의 요소들은 user-wrapper로 이름지정한 main태그로 다시 한 번 감쌌다

##### -CSS

1. 화면 중앙에 요소들을 배치하기 위해 main태그에 패딩값을 줌
2. 이미지들을 border-radius로 동그랗게 만들고 크기 조정함.이때 .group img에 스타일을 지정해준다.  
3. 상태를 표시해주는 동그라미를 만들기 위해 border-radius와 border값을 주고, 추후 이미지 요소위에 겹쳐지게 하기 위해 포지션으로 absolute를 준다.
그리고 컬러를 회색으로 지정해 기본 상태를 오프라인으로 만든다.
4. 부모요소인 .user에는 relative로 지정해준다.
5. 여러 유저들중 온라인으로 지정하고 싶은 요소의 순서를 
.user:nth-child(n) .status안에 넣는다. 뒤에 .status를 붙여야 유저 전체가 아닌 status요소에만 적용되게 된다.
6. 아래의 코드를 이용해서 4번째까지의 요소를 float로 띄우고 마진으로 사진사이의 간격을 준다.
```
.user:nth-child(-n+4) {
  float: left;
  margin-right: 20px;
}
```
7. 아래의 코드로 5번째 요소의 왼쪽에 float된 요소가 없게 만든 후 5~8번째 요소들을 float로 띄워준다.
```
.user:nth-child(5) {
  clear: left;
  margin-right: 20px;
}

.user:nth-child(n+5) {
 float: left;
  
  margin-right: 20px;
}
```
>아래의 코드 또한 똑같은 결과를 준다.
>이때 -n+3까지 설정하는 이유는 clear right값을 줬을때 3번째 요소까지 적용이 되기때문에 4번째 요소는 아무 영향을 받지않고 옆에 다음 요소를 배치하게 된다.
>이후 n+5로 float값을 주면 새로운 줄로 이동하게 되는것.

```
.user:nth-child(-n+3){
  float: left;
  clear: right;
  margin-right:20px;
  }

.user:nth-child(n+5){
float: left;
margin-right:20px;
} 
```
--------
#### Flex 활용하기

```
@supports(display:flex){

.user-wrapper{
  display: flex;
 flex-flow: row wrap-reverse;
 
}


}
```
supports 로 flex를 지원하는 브라우저에서는 위의 코드가 실행되게끔 우선순위에 배치해주고 user-wrapper요소를 flex로 설정해준 다음 row, wrap-reverse로 줄배치를 바꿔준다



