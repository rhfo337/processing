#README.md
## 심교수님 
float angle; //소수점이 있는 숫자를 표현
void setup() {
  size(700, 700, P3D); // P3D 프로세싱을 3차원으로 쓰기위함 
}
void draw() {
  background(0); // 배경을 검은색으로 
  camera(width/2, height/2, 400, width/2, height/2, 0, 0, 1, 0); //카메라 방향
  pointLight(155, 155, 155, width/2, height/2, -400); //모든 방향으로 골고루 빛을 비추는 조명 
  translate(width/2, height/2);

  rotateY(angle);
  rotateX(angle);
  rotateZ(angle);
  angle += 0.01;
  beginShape(QUADS);
  normal(0, 0, 1);
  fill(0, 0, 255); //채우기 
  vertex(-100, +100); // 꼭짓점 
  vertex(+100, +100);
  fill(255, 0, 0);
  vertex(+100, -100);
  vertex(-100, -100);
  endShape();
}
###프로세싱 예제 변화 
PGraphics pg;
void setup() {
  size(640, 360);
  pg = createGraphics(400, 200);
}
void draw() {
  fill(0, 12);
  rect(0, 0, width, height);
  fill(100);
  noStroke();
  ellipse(mouseX, mouseY, 60, 60);
  
  pg.beginDraw();
  pg.background(100);
  pg.noFill();
  pg.stroke(255);
  pg.ellipse(mouseX-80, mouseY-80, 80, 80);
  pg.endDraw();
  
  // Draw the offscreen buffer to the screen with image() 
  image(pg, -100, 60); 
}

####표정만들기 실패작... 좌표가 너무 어려웠습니다 ㅠ 
PShape robot = createShape(GROUP);
size(500,500);
background(100);
PShape head = createShape(ELLIPSE, 0, 0, 50, 50); // 타원형 눈
PShape headd = createShape(ELLIPSE, 50, 0, 50, 50); //타원형 눈 
PShape body = createShape(RECT, 0, 50, 30, 30); // 사각형 코 
PShape bodyy = createShape(RECT,-20, 130, 100, 100); // 정사각형 입 
robot.addChild(head);
robot.addChild(body);
robot.addChild(headd);
robot.addChild(bodyy);
translate(width/4, height/2);
shape(robot);

#####외계인이 X자하는 모양 
size(200,200);
rectMode(CENTER); 
rect(100,100,20,100);//몸통
ellipse(100,70,60,60); //  타원형 머리
ellipse(81,70,16,32); //  타원형 눈 
ellipse(119,70,16,32); // 타원형 눈 
line(90,150,80,160);  //오른쪽다리
line(110,150,120,160); /왼쪽다리
line(110,110,80,80);//왼손
line(89,110,150,80);//오른손 

######글자 위에서 아래로 내려오기 
PFont f;
  void setup() {
    size(800,300);
    textSize(128); //글자 크기 
    f = createFont("굴림", 34); //폰트 설정 및 사이즈 설정 
    textFont(f);
  }
  int i,dir=1,sp=1; // sp=스피드 
  void draw() {
    fill(0);
    background(255, 50, 255); //배경색 
    text("컴공 사랑합니다.",100, i++);
    if(i>width) dir=1; //위에서 아래로 내려오기 위한 식 
    i = i+dir*sp;
    if(keyPressed)
    sp=key-'0';
  }

...
####### 리포트 소감 
*프로세싱 예제를 이용하여 다양한 변화를 줄 수 있는것이 재미있는 것 같습니다. 

