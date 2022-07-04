Simple 3D button
---


```HTML
<a href="" class="link orange-btn">
<div class="inner-wrap">
<div class="front-3d">
<div class="content">custom text</div>
</div>
<div class="back-3d">
<div class="content">custom text</div>
</div>
</div>
</a>
``` 
CSS used in WP with Divi
```css
.link.orange-btn {
  text-decoration: none;
  perspective: 1000px;
}
.link.orange-btn .inner-wrap {
 display: inline-block;
  width: 400px;
  height: 60px;
  position: relative;
  transform-style: preserve-3d;
  transition: transform 0.6s cubic-bezier(0.2, 0.65, 0.4, 1);
}
.front-3d,
.back-3d {
  display: block;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
}
.orange-btn .front-3d .content,
.orange-btn .back-3d .content{
  width: 100%;
  height: 100%;
  font-size: 1.3rem;
  font-weight: 500;
  text-align: center;
  text-transform: uppercase;
  display: flex;
  flex-direction: column;
  justify-content: center;
-webkit-box-shadow: 0px 5px 10px 0px rgba(0,0,0,0.2);
-moz-box-shadow: 0px 5px 10px 0px rgba(0,0,0,0.2);
box-shadow: 0px 5px 10px 0px rgba(0,0,0,0.2);
}
.orange-btn .front-3d .content {
  color: #fff;
  background-color: #f79f1c;
  border: 2px solid #f79f1c;
}
.orange-btn  .back-3d .content {
  color: #f79f1c !important;
  background-color: #fff !important;
  border: 2px solid #f79f1c !important;
}
.front-3d {
  transform: rotateX(0deg) translateZ(30px);
}
.back-3d {
  transform: rotateX(-90deg) translateZ(30px);
}
.link:hover .inner-wrap {
  transform: rotateX(90deg);
}
```