## 5월 셋째주 과제 
#### Grid 활용하여 Apple 홈페이지 만들기
##### 카드 컴포넌트 만들기


###### 마크업
```
 <div class="card-wrapper">
      <div class="card ipad-pro">
      <div class="text">
        <h1>iPad Pro</h1>
        <p class="subhead">놀라우리만치 얇다.<br />엄청나게 강력하다</p>
        <p class="date">출시일 추후 공개</p>
      </div>
      
      <div class="link">
        <a class="more" href="https://www.apple.com/kr/ipad-pro/">더 알아보기</a>
        <a class="price" href="https://www.apple.com/kr/shop/buy-ipad/ipad-pro">가격보기</a>
      </div>
      </div>
```


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
3. 링크 버튼은 공통으로 적용시켜야 되는 부분은 


![image](https://github.com/30shanti/homework/assets/163807807/1d8f5367-85f4-4058-82f1-7140368537be)

![1](https://github.com/30shanti/homework/assets/163807807/eb2051b7-435b-42b5-b1fe-6d9ce4301ad5)

![2-3](https://github.com/30shanti/homework/assets/163807807/324c46a1-7f76-479c-b506-9a6329c10627)