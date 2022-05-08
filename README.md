# SVG ICON

## SVG

SVG(Scalable Vector Graphics)는 '2차원의 벡터 그래픽'을 표현하기 위해 탄생하였고 XML 기반의 포맷입니다.

1998년 W3C에서 개발을 하였고 그전에는 Microsoft의 "VML"와 Apple의 "PGML" 이라는 2차원의 백터 그래픽을 XML로 표현하는 언어가 있었습니다만, 두개다 W3C에서 채택하지 않았고 W3C는 SVG를 개발하여서 표준으로 채택하였습니다.

## 특징, 장/단점

### 장점

- 벡터기반으로 기존의 비트맵 기반의 포멧과 달리 사이즈가늘어나도 깨지지 않고 매끄럽게 표현됩니다.

- Web에서 Device의 Ratio를 대응하기 위해 기존 사이즈보다 x2된 사진으로 대응하는데 SVG를 사용하면 자동으로 대응되게 되어 원본과 x2를 모두 준비할 필요가 없습니다.

- XML 포맷으로 파일이 작성되므로 JS나 CSS로 조작이 가능합니다.

### 단점

**이미지가 복잡할수록 SVG만의 장점은 감소합니다.**

간단한 경우에는 JPG나 PNG보다 더 적은 용량일 수 있지만, Path가 많아지고 점점 더 무거워지면 기존이미지 포멧들보다 용량이 커질 수가 있습니다.

**이러한 단점을 보완하기 위해 SVG Optimizing을 위한 툴도 있습니다.**

> [GitHub - svg/svgo: ⚙️ Node.js tool for optimizing SVG files](https://github.com/svg/svgo)
> 
> [SVGOMG - SVGO's Missing GUI](https://jakearchibald.github.io/svgomg/)

### 특징

- HTML태그와는 달리 서로 밀어내지 않고 겹칩니다.**(display 개념이 아닙니다.)**

- 위치값 조절은 x,y로만 가능하며 CSS로 style지정은 가능하나 left,top등의 값은 먹지 않습니다.

- 태그의 역할이 뚜렷하여 HTML처럼 div로 모든걸 만들수 있는 것과는 대조적입니다.

- SVG안에 다른 SVG를 넣는 등 부모자식의 개념도 존재합니다.

## SVG ICON 사용하기

### SVG Tag

1.Img

일반 이미지와 같이 요소에서 SVG를 사용할 수 있습니다.

기존 이미지들과 동일하게 사용 할 수 있으며, 코드의 양이 적어 가독성이 뛰어납니다.

단점은 svg파일 속에 css 속성을 입힐 수가 없으며, 굉장히 작은 사이즈의 경우 비트맵 이미지처럼 렌더링이 될수있습니다.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="jOZbYKb" data-user="cho-i" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/cho-i/pen/jOZbYKb">
  SVG ICON-Img</a> by Lee cho i (<a href="https://codepen.io/cho-i">@cho-i</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

2.Inline

SVG 코드를 인라인하면 HTTP 요청은 저장되지만, 이미지는 브라우저에 캐시되지 않습니다. 조작이 가장 쉬운 방법이지만, 인라인 SVG 코드를 유지하는 것은 어려울 수 있습니다.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="bGLVaeZ" data-user="cho-i" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/cho-i/pen/bGLVaeZ">
  Untitled</a> by Lee cho i (<a href="https://codepen.io/cho-i">@cho-i</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

3.Background-image

태그가 아닌 div에 css를 이용하여, 백그라운드 이미지를 삽입할 수 있습니다. 기존의 스프라이트 이미지를 활용하는 방법과 동일하게 사용할 수 있으며, 이미지와 속성이 동일하기 때문에 작업에 어려움이 없습니다.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="zYRvREL" data-user="cho-i" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/cho-i/pen/zYRvREL">
  Untitled</a> by Lee cho i (<a href="https://codepen.io/cho-i">@cho-i</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>



### Background-image Sprite 작업하기

1. https://jakearchibald.github.io/svgomg/ 에 SVG파일 업로드하거나 에디터에서 SVG파일 코드로 확인 후 복사한다.

2. sprite.svg파일 내 최상단 svg태그(부모) 내 svg(자식) 코드를 붙여 넣는다.

3. html파일 내 `<i class="icon-facebook"></i>`  icon-(svg이름)으로 사용한다.



#### 작업시 유의사항

**<u>색이 이상하거나 적용안될때</u>**

- 적용이 안되는 케이스는 필터를 지우고 fill/stroke 색상을 직접적으로 넣는식으로 변경
- 감싸고있는 g 태그에 fill="none" 지움



## 기대효과

고해상도의 PNG는 일반적으로 HDPI 디스플레이에 렌더링이 될 때 크기가 매우 큽니다. 우리는 배경이 없는 이미지를 사용하기 위해서 PNG를 사용해왔고 그렇기 때문에 용량이 상대적으로 큰 PNG를 로드하는데 시간이 오래 걸리기 때문에 브라우저의 로딩 속도가 느려지는 것입니다.

SVG는 코드로 이루어져 있기 때문에 바이트도 안 되는 크기로 이루어져 있어 PNG나 JPG의 이미지보다 용량적인 측면에서 훨씬 적어 웹사이트의 로딩 속도를 훨씬 빠르게 만들어줍니다.

### 사이트 로딩의 출력 차이

브라우저가 로딩하려고 할 때마다 서버에 HTTP 요청을 해야 합니다. 웹페이지에 이미지가 많을수록 더 많은 HTTP 요청이 이루어져 사이트 속도가 느려지는 것입니다.

SVG는 크기가 작을 뿐만 아니라 SVG코드를 HTML의 인라인에 포함하여 HTTP 요청을 제거할 수 있어 유연성이 빨라지는 것입니다.

> [Hypertext Transfer Protocol - Wikipedia](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#HTTP_session)

이전에 PNG를 활용할 때 아이콘들을 하나의 파일에 합쳐서 위치 값만으로 나머지를 숨기고 표시해서 아이콘을 보이게 했던 이유도 로딩 속도와 용량 때문입니다.

## **참고**

> https://brunch.co.kr/@kkak10/3
> 
> https://brunch.co.kr/@ggk234/11
> 
> [SVG Icons - 인코덤, 생물정보 전문위키](http://www.incodom.kr/SVG_Icons)
> 
> [SitePoint](https://www.sitepoint.com/use-svg-image-sprites/)
> 
> [How to use SVG sprites in img[src] and css backgrounds · GitHub](https://gist.github.com/darsain/3a8e344f655621ce1d4f)
> 
> https://medium.com/design-code-repository/cutup-5-icon-with-css-svg-sprite-ea01eeb8bb41
> 
> [SVG 스프라이트 - Graphics ARIA Guidebook](https://a11y.gitbook.io/graphics-aria/svg-graphics/sprites)
> 
> https://tecoble.techcourse.co.kr/post/2021-10-24-svg-viewBox/
