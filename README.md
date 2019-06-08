var imgsAndando=[]
var anima;
var imgsAtirando=[]
var contFrame = 0;
var paraFrames=0;
var x=10
var y =10
var raioP=10
var estadoDisparo = false;
var raioD=5
var tempo=0
var raioIF=15
var vidasif=20
var xif=350
var yif=200
var tela=1
var xin2=[]
var yin2=[]
var qtdObjetosn2=10
var vidas=4
var pontos=0
var nivel=1
var vxi=[]
var vyi=[]
var qtdObjetos=10
var raioO=15
var raioP=10
var x=10
var y=200
var xd
var yd
var bpontos=9
function preload(){
for(i=0 ; i<4 ;i++){
 imgsAtirando[i]=loadImage("Cowboy4_shoot_"+i+".png");} 
  for(i=0 ; i<4 ;i++){
 imgsAndando[i]=loadImage("Cowboy4_walk without gun_"+i+".png");} 
                           }
function setup(){
  frameRate(30)
  createCanvas(600,400);}
 function draw() {
 if(tela == 1){
    background(150)
   textSize(39)
   text('Bem vindo ao jogo,jogador!',10,50);
  textSize(13)
  text('No nivel 1 o objetivo do jogo é eliminar todos os alvos antes que eles cheguem\n do outro lado da tela. ',10,100);
  text('No nivel 2 o objetivo é apenas chegar ao outro lado.',10,150)
   text('No nivel 3 voce tem que deixar a vida do inimigo em zero,mas se o tempo chegar \n em 40 segundos voce perde,além disso quanto mais no centro voce acertalo mais \n pontos de vida ele ira perder.',10,190) 
  text('Aperte ENTER para ir ao inicio do jogo.',10,330)
   text('Voce pode atirar usando CTRL e se movimentar usando as setas do teclado.\n boa sorte.',10,250)
  if ( keyIsDown(ENTER) ){
    tela=2;
  }
}
if(tela==2){

  background(200)
   ellipse(x,y,1*raioP,1*raioP)
   anima=imgsAndando[contFrame];
  noStroke()
  imageMode(CENTER)
  image(anima,x,y,50)
  paraFrames++
  if(paraFrames>7){
  contFrame++;
    paraFrames=0;}
  if(contFrame>3){
    contFrame=0}
if ( keyIsDown(CONTROL) ){
   anima=imgsAtirando[contFrame];
  noStroke()
  imageMode(CENTER)
  image(anima,x,y,50)
  contFrame++;
  if(contFrame>3){
    contFrame=0}
}
if ( keyIsDown(RIGHT_ARROW) )
  {
    x=x+4
  }
   if ( keyIsDown(LEFT_ARROW) )
  {
    x=x-4
  }
  if ( keyIsDown(UP_ARROW) )
  {
    y=y-4
  }
    if ( keyIsDown(DOWN_ARROW) )
  {
    y=y+4
  }
   ellipse(xd,yd,1*raioD,1*raioD)
  if ( keyIsDown(CONTROL) && ! estadoDisparo)
  {
    xd=x
    yd=y
    estadoDisparo = true;
  }

if( estadoDisparo ) {
  ellipse(xd,yd,1*raioD,1*raioD)
  xd=xd+10;
}
  if(xd > 500)
  {
    estadoDisparo=false
  }
}
}
  
  
  
