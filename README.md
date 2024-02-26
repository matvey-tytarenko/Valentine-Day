## Valentine Day's
___
![](./website.png)
___
**[Design was copied from this video](https://youtu.be/S62Xz2Qp6Hs?si=xEgvjhxA_qH0giDl)**
___
**Source Code:**
#### HTML
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>С днём святого валентина</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div class="container">
      <div class="heart">
      </div>
    </div>
    
    <!-- JS -->
    <script>
      function rain() {
        let heart = document.querySelector(".heart");
        let e = document.createElement("div");

        e.classList.add("drop");
        heart.appendChild(e);

        let left = Math.floor(Math.random() * 300);
        let duration = Math.random() * 0.5;

        e.style.left = left + "px";
        e.style.animationDuration = 1 + duration + "s";

        setTimeout(() => {
          heart.removeChild(e);
        }, 5000);
      }
      setInterval(function () {
        rain();
      }, 50);
    </script>
  </body>
</html>
```
___

#### CSS
```css

@import url(https://fonts.googleapis.com/css?family=Poppins:100,100italic,200,200italic,300,300italic,regular,italic,500,500italic,600,600italic,700,700italic,800,800italic,900,900italic);

:root {
  --bg: radial-gradient(#4c0c0c, #000);
  --border: rgba(255, 255, 255, 0.05);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background: var(--bg);
}

.container {
  position: relative;
  height: 430px;
  width: 100%;
  display: flex;
  justify-content: center;
  border-bottom: 1px solid var(--border);
  -webkit-box-reflect: below 1px
    linear-gradient(transparent, transparent, transparent, transparent, #0005);
}

.heart {
  position: relative;
  width: 300px;
  height: 300px;
}

.heart::before {
  content: "";
  position: absolute;
  width: 200px;
  height: 300px;
  background: #6a1629;
  border-top-left-radius: 100px;
  border-top-right-radius: 100px;
  rotate: 315deg;
  z-index: 1000;
  animation: animate 2s steps(1) infinite;
}
.heart::after {
  content: "";
  position: absolute;
  top: -20px;
  left: 92px;
  width: 200px;
  height: 300px;
  background: #6a1629;
  border-top-left-radius: 100px;
  border-top-right-radius: 100px;
  rotate: 45deg;
  z-index: 1000;
  animation: animate 2s steps(1) infinite;
}

.title {
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    top: -100px;
    color: rgb(255, 42, 0);
    font-family: 'Poppins', sans-serif;
    text-transform: uppercase;
    filter: drop-shadow(0 0 50px #f00) drop-shadow(0 0 150px #f00);
}

.drop {
  position: absolute;
  width: 30px;
  height: 30px;
  top: 40px;
  filter: drop-shadow(5px 5px 10px #000) drop-shadow(0px 0px 10px #f00);
  transform-origin: bottom;
  animation: rain 4s linear forwards;
}
.drop::before {
  content: "";
  position: absolute;
  width: 20px;
  height: 30px;
  background: #f00;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
  transform-origin: bottom center;
  rotate: -45deg;
  z-index: 100000;
}
.drop::after {
  content: "";
  position: absolute;
  bottom: 3px;
  width: 30px;
  height: 20px;
  background: #f00;
  border-top-right-radius: 20px;
  border-bottom-right-radius: 20px;
  transform-origin: bottom center;
  rotate: 315deg;
  z-index: 100000;
}

@keyframes animate {
  0%,
  94%,
  100% {
    filter: none;
  }
  95% {
    filter: drop-shadow(0 0 50px #f00) drop-shadow(0 0 150px #f00);
    background: #f00;
  }
}
@keyframes rain {
  0% {
    top: 40px;
    opacity: 1;
    scale: 1;
  }
  70% {
    top: 400px;
    opacity: 1;
  }
  80% {
    top: 400px;
  }
  100% {
    top: 400px;
    opacity: 0;
    scale: 0;
  }
}
```