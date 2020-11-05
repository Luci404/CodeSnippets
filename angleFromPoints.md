### float AngleFromPoints(vector2 p0, vector2 p1, vector2 p2)
> Center point is p1; angle returned in Radians.

#### VEX
```c
float AngleFromPoints(vector2 p0; vector2 p1; vector2 p2) {
    float b = pow(p1.x-p0.x,2) + pow(p1.y-p0.y,2);
    float a = pow(p1.x-p2.x,2) + pow(p1.y-p2.y,2);
    float c = pow(p2.x-p0.x,2) + pow(p2.y-p0.y,2);
    return acos((a+b-c) / sqrt(4*a*b));
}

vector2 p0 = {0, 0};
vector2 p1 = {-6, 30};
vector2 p2 = {22, 29};

printf("Angle: %d", degrees(AngleFromPoints(p0,p1,p2)));
```

#### JavaScript
```javascript
function AngleFromPoints(p0,p1,p2) {
    var b = Math.pow(p1.x-p0.x,2) + Math.pow(p1.y-p0.y,2),
        a = Math.pow(p1.x-p2.x,2) + Math.pow(p1.y-p2.y,2),
        c = Math.pow(p2.x-p0.x,2) + Math.pow(p2.y-p0.y,2);
    return Math.acos( (a+b-c) / Math.sqrt(4*a*b) );
}

var p0 = { 'x': 10, 'y': 20 };
var p1 = { 'x': 20, 'y': 10 };
var p2 = { 'x': 60, 'y': 20 };
var angle = AngleFromPoints(p0,p1,p2);

console.log(angle * (180 / Math.PI));
```
