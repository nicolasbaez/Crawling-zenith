# Crawling-zenith
May i see your future?

![buh](https://github.com/nicolasbaez/Crawling-zenith/blob/main/xp013.gif)
```javascript
w = k = 500;
setup = (_) => createCanvas(w, w, WEBGL);
draw = (_) => {
  colorMode(RGB, 6);
  rotateX(k);
  rotateY(k / 2);
  clear();
  for (i = 0; i <= 3; i += 0.1)
    for (j = 0; j < 6; j += 0.1) {
      r = (noise(i, j, k) * w) / 2;
      noFill();
      stroke(i, j, 6);
      push();
      translate(r * sin(i) * cos(j), r * sin(i) * sin(j), r * cos(i));
      box(9);
      pop();
    }
  k -= 0.02;
};

keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp013.gif", 314, { delay: 0, units: "frames" });
  }
};
