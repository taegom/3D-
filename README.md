3D 관련 속성 사용해서 실습
## 포켓몬 회전
<!DOCTYPE html>
<html lang="ko-KR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title></title>
    <style>
      :root {
        /* 원의 둘레 = 340px * 7 */
        /* 지름 = 원주 / 파이 / 2  */
        --translateZ: calc((340px * 7) / 3.14 / 2);
      }

      * {
        margin: 0;
        padding: 0;
        list-style: none;
      }

      @keyframes rotate {
        to {
          transform: translate(-50%, -50%) rotateY(1turn);
        }
      }

      div {
        height: 100vh;
        perspective: 800px;
      }

      .list-item {
        position: relative;
        width: 340px;
        height: 400px;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        transform-style: preserve-3d;

        animation: rotate 5s infinite linear;
      }

      .list-item li {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        backface-visibility: hidden;
      }

      li img {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }

      li:nth-child(1) {
        transform: rotateY(0) translateZ(var(--translateZ));
      }

      li:nth-child(2) {
        transform: rotateY(calc(360deg / 7)) translateZ(var(--translateZ));
      }

      li:nth-child(3) {
        transform: rotateY(calc((360deg / 7) * 2)) translateZ(var(--translateZ));
      }

      li:nth-child(4) {
        transform: rotateY(calc((360deg / 7) * 3)) translateZ(var(--translateZ));
      }

      li:nth-child(5) {
        transform: rotateY(calc((360deg / 7) * 4)) translateZ(var(--translateZ));
      }

      li:nth-child(6) {
        transform: rotateY(calc((360deg / 7) * 5)) translateZ(var(--translateZ));
      }

      li:nth-child(7) {
        transform: rotateY(calc((360deg / 7) * 6)) translateZ(var(--translateZ));
      }
    </style>
  </head>
  <body>
    <div>
      <ul class="list-item">
        <li><img src="../images/ev.png" alt="" /></li>
        <li><img src="../images/jammanbo.png" alt="" /></li>
        <li><img src="../images/mazayoung.png" alt="" /></li>
        <li><img src="../images/mobugi.png" alt="" /></li>
        <li><img src="../images/nyaong.png" alt="" /></li>
        <li><img src="../images/pulin.png" alt="" /></li>
        <li><img src="../images/weirdseed.png" alt="" /></li>
      </ul>
    </div>
  </body>
</html>
![poketmon](https://github.com/user-attachments/assets/9359c92d-c230-40d0-b44e-1849173de5e9)

## Card 만들기
<!DOCTYPE html>
<html lang="ko-KR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>card</title>
    <style>
        body {
            background-color: rgb(213,201,221);
        }
      .container {
        width: 100px;
        perspective: 1000px;
        padding: 100px;
      }

      .item {
        width: 200px;
        height: 250px;
        background-color: royalblue;
        transition: all 1s;
        transform-style: preserve-3d;
      }

      .item:hover {
        transform: rotateY(900deg) scale(1.5);
        transition-duration: 0.7s;
      }

      .item::before,
      .item::after {
        position: absolute;
        width: 100%;
        height: 100%;
        color: #fff;
        font-weight: 600;
        font-size: 24px;
        display: flex;
        justify-content: center;
        /* align-items: center; */
        
        backface-visibility: hidden;
      }

      .item::before {
        background-image: url(./모코코/1.png);
        background-size: contain;
        background-repeat: no-repeat;
        content: "김태윤";
        background-color: #354f52;
        align-items: end;
      }

      .item::after {
        content: "(☞ﾟヮﾟ)☞       잘부탁드립니다";
        font-size: 14px;
        background-color: #a7c6da;
        transform: rotateY(180deg);
        align-items: center;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="item"></div>
    </div>
  </body>
</html>

