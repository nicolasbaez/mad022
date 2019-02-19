# mad022
dimensional portal loop

![mad022](https://github.com/nicolasbaez/mad022/blob/master/mad022.gif)

```processing
int ancho;
int z;
int depth=1024;
int k=0;
void setup() {
  size(512, 256, P3D);
  background(255);
  stroke(255);
  ancho=width/4;
}
void draw() {
  background(255);
  translate(width/2, height/2, -z);
  rotate(radians(z));
  rotateX(radians(z));
  rotateY(radians(z));
  for (int i=-width/2; i<width/2; i+=ancho) {
    for (int j=-height/2; j<height/2; j+=ancho) {
      fill(random(255), random(255), random(255));
      rect(i, j, map(z, 0, depth, ancho, 0), map(z, 0, depth, ancho, 0));
    }
  }
  z=int(map(sin(radians(k)), -1, 1, 0, depth));
  k++;
  if (k>=360&&k<720) {
    saveFrame("gif/mad022-######.png");
  }
}
```
