---
layout: default
title: Add design to your App with HTML and CSS
permalink: design-html-css
---

1.헤더를 디자인합니다.

+ `app/assets/stylesheets/application.css` 파일에 아래와 같이 추가합니다:

    ```
    .navbar {
        min-height: 38px;
      background-color: #f55e55;
    }
    ```

  새로고침 버튼을 눌러서 페이지를 보면 디자인이 바뀝니다. 
    헤더의 글꼴과 색깔을 바꿀 수 있습니다. 색깔 참조표는 
    [http://color.uisdc.com/](http://color.uisdc.com/)를 참고합니다.

    **Coach: ** `display` 프라퍼티와 인라인, 블록 엘리먼트를 설명하세요.

+ 파일 맨 끝에 아래와 같이 코드를 추가합니다：

    ```
    .navbar a.brand { font-size: 18px; }
    .navbar a.brand:hover {
     color: #fff;
     background-color: transparent;
     text-decoration: none;
    }
    ```

    **Coach: ** 링크의 4가지 상태를 설명하세요.


2.테이블을 디자인합니다.

 + 트위터 [부트스트랩](http://www.bootcss.com/)을 사용하여 
   테이블을 꾸밉니다. 
   app/views/ideas/index.html.erb 파일에서 아래 코드를 찾아서 :

   ```
   <table>
   ```

   다음과 같이 수정합니다.

   ```
   <table class="table">
   ```

 + 아래와 같이 수정하여 사진 크기를 바꿉니다.

     ```
     <%= image_tag(idea.picture_url, :width => 600) if idea.picture.present? %>
     ```

     width를 수정하여 어떻게 보이는지 확인합니다.


 + app/assets/stylesheets/ideas.css.scss 파일의 맨 끝에 아래와 같이 추가합니다:

  ```
  .container a:hover {
    color: #f55e55;
    text-decoration: none;
    background-color: rgba(255, 255, 255, 0);
  }
  ```


 + `background-image` 프라퍼티를 백그라운드에 추가합니다.
   몇가지 사례는 
   [http://subtlepatterns.com/](http://subtlepatterns.com/)를 참고합니다.


3.푸터에 스타일을 추가합니다.

+ app/assets/stylesheets/application.css 파일 맨 끝에 다음과 같이 추가합니다:

    ```
    footer {
      background-color: #ebebeb;
      padding: 30px 0;
    }
    ```

    `footer`에 다른 것을 넣어보고 위치를 조정해봅니다.

4.버튼에 스타일을 추가합니다.

  + 브라우저로 
    [http://localhost:3000/ideas/new](http://localhost:3000/ideas/new)
    이동하여 `Create Idea` 버튼을 찾습니다.

   app/assets/stylesheets/ideas.css.scss 파일에 아래와 같이 추가합니다.

   ```
   .container input[type="submit"] {
      height: 30px;
      font-size: 13px;
      background-color: #f55e55;
      border: none;
      color: #fff;
    }
   ```

   **Coach** css에서 `border`를 어떻게 사용하는지 설명하세요. 
     버튼 스타일을 둥근 모양으로 바꾸고 그림자와 색깔을 바꿔봅니다.
