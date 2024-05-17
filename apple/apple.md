## 5월 셋째주 과제 
#### Grid 활용하여 Apple 홈페이지 만들기
##### 카드 컴포넌트 만들기


###### 마크업
```
<div class="card-wrapper" role="group">
      <div class="card ipad-pro" aria-labelledby="ipad-pro-title">
      <div class="text">
        <h1 id="ipad-pro-title">iPad Pro</h1>
        <p class="subhead">놀라우리만치 얇다.<br />엄청나게 강력하다</p>
        <p class="date">출시일 추후 공개</p>
      </div>
      
      <div class="link">
        <a class="more" href="https://www.apple.com/kr/ipad-pro/" aria-label="iPad Pro 더 알아보기">더 알아보기</a>
        <a class="price" href="https://www.apple.com/kr/shop/buy-ipad/ipad-pro" aria-label="iPad Pro 가격보기">가격보기</a>
      </div>
      </div>

```
div로 마크업을 하고 접근성을 높이기 위해 aria와 role속성을 이용했다.

```
.card{
  padding-top: var(--large-spacing);
  height: var(--size);
  gap:var(--small-spacing) ;
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  color: var(--white);
  background-image: image-set(
          url('/apple/products/ipad_pro.jpeg') 1x,
          url('/apple/products/ipad_pro_2x.jpeg') 2x
      );
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
}

```
1. 부모요소를 flex모델로 지정해 자식요소들을 column으로 센터정렬했다.
이미지는 크기별로 2장 삽입했다.

```
 /* 글자 */
  
  .text{
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  gap:var(--x-small-spacing);
  
  h1{
  font-size: var(--large-text);
  
  }
  
  .subhead{
    font-size: var(--base-text);
    /* margin-bottom: var(--x-small-spacing); */
    line-height: var(--line-normal);
    font-weight: 600;
    text-align: center;
  }
  
  .date{
    font-size: var(--small-text);
    color: var(--gray);
    font-weight: 600;
    
    }
  }

```
2. 마찬가지로 글자영역의 부모요소에도 flex를 적용시키고 폰트 굵기가 얇아보여 임의로 변경하였다.

```
 /* 링크 버튼*/
  .link{
    gap: var(--base-spacing);
    display: flex;
  
    .more, .price{
      
      font-size: var(--xx-small-text);
      padding: var(--x-small-spacing);
      border-radius: 15px;
  }
  .more{
    background-color: var(--blue-300);
    color: white;
  padding: var(--x-small-spacing) var(--small-spacing);
  
  }
  .price{
  color: var(--blue-300);
  border: 1px solid var(--blue-300);
  padding: var(--x-small-spacing) var(--small-spacing);
  }
  
  }
  
```
3. 링크 버튼은 공통으로 적용시켜야 되는 부분은 묶어서, 디자인이 다른 부분은 따로 적용시켰다.

###### 결과
![image](https://github.com/30shanti/homework/assets/163807807/1d8f5367-85f4-4058-82f1-7140368537be)

##### 홈페이지 레이아웃 
```
 <div class="grid">

        <div class="card watch" role="group" aria-labelledby="watch-title">
          <div id="watch-title" class="text">
            <h1>WATCH</h1>
            <p class="subhead">보다 똑똑. 보다 또렷. 보다 강력.</p>
          </div>
          <div class="link">
            <a class="more" href="https://www.apple.com/kr/ipad-pro/" aria-label="Apple Watch 더 알아보기">더 알아보기</a>
            <a class="price" href="https://www.apple.com/kr/shop/buy-ipad/ipad-pro" aria-label="Apple Watch 가격보기">가격보기</a>
          </div>
          </div>

      <div class="card iphone15" role="group" aria-labelledby="iphone15-title">
        <div class="text">
          <h1 id="iphone15-title">iPhone 15</h1>
          <p class="subhead">새로운 카메라.<br />새로운 디자인.<br />새로움이 물씬.</p>
        </div>
        <div class="link">
          <a class="more" href="https://www.apple.com/kr/ipad-pro/" aria-label="iPhone 15 더 알아보기">더 알아보기</a>
          <a class="price" href="https://www.apple.com/kr/shop/buy-ipad/ipad-pro" aria-label="iPhone 15 가격보기">가격보기</a>
        </div>
        </div>

        <div class="card airpods-pro" role="group" aria-labelledby="airpods-pro-title">
          <div class="text">
            <h1 id="airpods-pro-title">airPods Pro</h1>
            <p class="subhead">전에 없던 청취 경험.<br />적응형 오디오.</p>
          </div>
          <div class="link">
            <a class="more" href="https://www.apple.com/kr/ipad-pro/" aria-label="AirPods Pro 더 알아보기">더 알아보기</a>
            <a class="price" href="https://www.apple.com/kr/shop/buy-ipad/ipad-pro" aria-label="AirPods Pro 가격보기">가격보기</a>
          </div>
          </div>

        <div class="card macbook-air" role="group" aria-labelledby="macbook-air-title">
        <div class="text">
          <h1 id="macbook-air-title">MacBook Air</h1>
          <p class="subhead">날렵하게. 강력하게. M3답게.</p>
        </div>
        <div class="link">
          <a class="more" href="https://www.apple.com/kr/ipad-pro/" aria-label="MacBook Air 더 알아보기">더 알아보기</a>
          <a class="price" href="https://www.apple.com/kr/shop/buy-ipad/ipad-pro" aria-label="MacBook Air 가격보기">가격보기</a>
        </div>
        </div>

      
      </div>
```
1. 화면이 커졌을 때 그리드를 적용하기 위해 적용대상인 요소들을 묶었다.
나중에 짝수번째 요소들은 링크 버튼의 색상을 nthchild를 활용해 변경예정인데 부모요소로 인해 순서를 정할 때 원활히 진행되지 않음을 대비해 마크업 순서를 nth-child가 적용되게끔 변경했다.

```
.card-wrapper{
display: flex;
flex-flow: column nowrap;
gap: 10px;


.grid{
  
  display: flex;
  flex-flow: column nowrap;
  gap: 10px;

}

```
2. 모든 요소를 감싸고 있는 card-wrapper에 flex모델을 주고 column으로 배치 후 카드간의 간격을 띄우기 위해 갭을 줬다. 


```
/* 이미지 변경 */
.ipad-air{

  background-image: image-set(
          url('/apple/products/ipad_air.jpeg') 1x,
          url('/apple/products/ipad_air_2x.jpeg') 2x
      );
}
.iphone15-pro{

  background-image: image-set(
          url('/apple/products/iphone15_pro.jpeg') 1x,
          url('/apple/products/iphone15_pro_2x.jpeg') 2x
      );
}
.iphone15{

  background-image: image-set(
          url('/apple/products/iphone15.jpeg') 1x,
          url('/apple/products/iphone15_2x.jpeg') 2x
      );
}
.watch{

  background-image: image-set(
          url('/apple/products/apple_watch.jpeg') 1x,
          url('/apple/products/apple_watch_2x.jpeg') 2x
      );
}
.macbook-air{

  background-image: image-set(
          url('/apple/products/macbook_air.jpeg') 1x,
          url('/apple/products/macbook_air_2x.jpeg') 2x
      );
}
.airpods-pro{

  background-image: image-set(
          url('/apple/products/airpods_pro.jpeg') 1x,
          url('/apple/products/airpods_pro_2x.jpeg') 2x
      );
}

.iphone15{
  order: -1;
}
.watch{
  order: 0;
}
.macbook-air{
  order: 1;
}
.airpods-pro{
  order: 2;
}


}
```
3. 각각의 카드의 이미지를 변경해주고 마크업 단계에서 조정했었던 그리드 요소들을 원래 배치해야되는 순서에 맞게 재조정했다.

```
/* 짝수 번째 링크/텍스트 버튼 색상 변경 */
.card:nth-child(even){
  .text{
h1, p.subhead{
  color: var(--black);
}

  }
  .link{

  .more{
    background-color: var(--black);
    color: white;
  padding: var(--x-small-spacing) var(--small-spacing);
  
  }
  .price{
  color: var(--black);
  border: 1px solid var(--black);
  padding: var(--x-small-spacing) var(--small-spacing);
  }
  }
}
```
4. nth-child를 활용하여 짝수번째 오는 이미지들의 링크 버튼의 색깔을 바꿔줬다.

###### 결과
![1](https://github.com/30shanti/homework/assets/163807807/eb2051b7-435b-42b5-b1fe-6d9ce4301ad5)

###### 1024px 이상인 스크린에서의 배치
```
@media(min-width:1024px){
.card-wrapper{

  .iphone15-pro{

    background-image: image-set(
            url('/apple/products/iphone15_pro_wide.jpeg') 1x,
            url('/apple/products/iphone15_pro_wide_2x.jpeg') 2x
        );
  }

  .grid{
display: grid;
grid-template-columns: 1fr 1fr;
  }
}
.iphone15{
  order: -1;
}
.watch{
  order: 0;
}
.macbook-air{
  order: 1;
}
.airpods-pro{
  order: 2;
}
}
```
1. media를 활용하여 1024px이상인 스크린에서는 아이폰 15 프로의 이미지를 가로로 바꾸고 4개의 카드를 그리드로 배치한다.
마크업상의 순서도 바꿔준다.

######결과

![2-3](https://github.com/30shanti/homework/assets/163807807/324c46a1-7f76-479c-b506-9a6329c10627)