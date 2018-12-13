### tacking.js
---
https://github.com/eduardolundgren/tracking.js

```
bower install tracking
npm install tracking

bower install tracking-elements --save
```

```
<!doctype html>
<html>
<head>
 <meta charset="utf-8">
 <title>tracking.js - first tracking</title>
 <script src="../build/tracking-min.js"></script>
</head>
<body>
  <video id="myVideo" width="400" height="300" preload autoplay loop muted></video>
  <script>
  
  var colors = new tracking.ColorTracker(['magenta', 'cyan', 'yellow']);
  colors.on('track', function(event){
    if(event.data.length){
    } else {
      event.data.forEach(function(rect){
        console.log(rect.x, rect.y, rect.height, rect.width, rect.color);
      });
    }
  });
  tracking.track('#myVideo', colors);
  </script>
</body>
</html>

<script src="bower/platfrom/platform.js"></scirpt>
<link rel="import" href="../src/image-object-traking.html">
<img is="image-object-traking" target="face" src="assets/faces.png" />
<script>
var img = document.querySelector('img');
img.addEventListener('track', funciton(event){
  event.detail.data.forEach(function(rect){
    plotRectangle(img, rect);
  });
});
function plotRectangle(el, rect){
  var div = document.createElement('div');
  div.style.position = 'absolute';
  div.style.border = '2px solid' + (rect.color || 'magenta');
  div.style.width = rect.width + 'px';
  div.style.height = rect.height + 'px';
  div.style.left = el.offsetLeft + rect.x + 'px';
  div.style.top = el.offsetTop + rect.y + 'px';
  document.body.appendChild(div);
  return div;
}
</script>
```

```js
var myTracker = new tracking.Tracker('target');

myTracker.on('track', funciton(event){
  if(event.data.length === 0){
  } else {
    event.data.forEach(function(data){
    });
  }
});

var trackerTask = tracking.track('#myVideo', myTracker);

trackerTask.stop();
trackerTask.run();

var colors = new tracking.ColorTracker(['magenta', 'cyan', 'yellow']);

colors.on('track', function(event){
  if(event.data.length === 0){
  } else {
    event.data.forEach(function(rect){
      // rect.x, rect.y, rect.height, rect.width, rect.color
    });
  }
});

tracking.track('#myVideo', colors);

tracking.ColorTracker.registerColor('green', function(r, g, b){
  if(r < 50 && g > 200 && b < 50){
    return true;
  }
  return false;
});

var objects = new tracking.ObjectTracker(['face', 'eye', 'mouth']);

object.on('track', function(event){
  if(event.data.length === 0){
  } else {
    event.data.forEach(function(rect){
    });
  }
});

tracking.track('#myVideo', objects);

var MyTracker = function(){
  MyTracker(this, 'constructor');
}
tracking.inherits(MyTracker, tracking.Tracker);

var MyTracker = function(){
  MyTracker.prototype.track = function(pixels, width, height){
    this.emit('track', {
    });
  }
}

var myTracker = new tracking.MyTracker();

myTracker.on('track', function(event){
});

tracking.track('#myVideo', myTracker);

var corners = tracking.Fast.findCorners(pixels, width, height);

var descriptors1 = tracking.Brief.getDescriptors(pixels, width, corners1);
var descriptors2 = tracking.Brief.getDescriptors(pixels, width, corners2);

var matches = tracking.Brief.reciprocalMatch(corners1, descriptors1, corners2, descriptors2);

tracking.Image.horizontalConvolve(pixels, width, height, weightsVector, opaque);
tracking.Image.verticalConvolve(pixels, width, height, weightsVector, opaque);
tracking.Image.separableConvolve(pixels, width, heigth, horizWeights, vertWeights);

tracking.Image.grayscale(pixels, width, height, fillRGBA);

tracking.Image.blur(pixels, width, height, diameter);

tracking.Image.computeIntergralImage(
  pixels, width, height, opt_integralImage, opt_integralImageSquare,
  opt_tiltedIntegralImage, opt_integralImageSobel);

tracking.Image.sobel(pixels, width, height);

tracking.ViolaJones.detet(pixels, width, height, initailScale, scaleFactor, stepSize, edgesDensity, classifier);
```

