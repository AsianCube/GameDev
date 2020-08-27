







<!DOCTYPE html>
<html>
    <head>
        <title>isFingerChoped</title>
    </head>
    <body>
     <div id="bgImg">
   Be Focus to Score High
     </div>
    <div id="score">
        
    <h2>Score:</h2>
        
    <h2 id="score0"> 0</h2>
    </div>
        <div class="chopBoard">
            <div id="knife">
                <img src="https://i.postimg.cc/d1DSNpzD/Pics-Art-06-26-06-15-47-min.png" alt="blade" id="bladeImg">
            </div>
            <div id="finPos" ontouchstart="isFinPlaced(event)" ontouchend="safe(event)">
                
            </div>
            <div class="designBoard">
                <div id="sideCut">
                    
                </div>
            </div>
            <div id="info">
                Place Your Finger Until Blade don't move 
            </div>
        </div>
    <div id="window">
        
        <div id=scoreBoard>
        <div id="report">
                No Name : 
            </div>
            <div id="isLose">
            
            <span id="loseInfo">
              Blade Hit on Finger 😭
            </span>
              <span style="letter-spacing:3px;position:absolute;top:50px;left:25px;color:red;font-weight:bold;font-size:21px;" id="go">Game Over</span>
            </div>
            <div id="scoreTotal">
                
            </div>
            <button onclick="retry()">Retry</button>
            <div id="challenge">
            <h3>Challenge others by sharing score report</h3>
        </div>
        </div>
        
    </div>
    <div id="input" onclick="input()">
        Enter Name Here 
    </div>

    <script>
  /* Starting */
  /* Message */
  
  alert('Be Patience \nImages needs time To Show \n#play&Fun 😀\n');
  alert('Welcome!!\n\nYour every like or dislike Precious♥️🤩\n\nPlease,Don\'t forget it😔');
  
 /* Making Objects of HTML element */
 
        let  knife=document.getElementById('knife');
        let finPos=document.getElementById('finPos');
        let info=document.getElementById('info');
        let scoreB=document.getElementById('score0');
        let scoreOnB=document.getElementById('scoreTotal');
        let sBoard=document.getElementById('window');
        let userLoseInfo=document.getElementById('loseInfo');
        let inputI=document.getElementById('input');
        let quote=document.getElementById('bgImg');
        let report=document.getElementById('report');

 /* Variables of this nice Game !! */

   let isLost=false;
   let timeUp=timeUp1=null;
   let topInc=2;
   let score=0;
   let scoreInc=false;
   let isFunRun=false;
   
 /* Function run on touch of User */
  
    function isFinPlaced(e)
    {
    info.innerHTML="Finger Placed ☑️\nHold it ";
        rand=Math.floor(Math.random()*(4-1))*(900);
                timeUp1=setTimeout(knifeDrop,rand);
    }
    
 /* Function Run after completion of                            delaying timeout To drop Blade */

   function knifeDrop()
   {
      timeUp=setInterval(knifeMove,3);
   }
  
 /* Function Run on touch end */   
 
    function safe(e)
    {
        clearInterval(timeUp );
        clearInterval(timeUp1);
        timeUp1=timeUp=null;
        topInc=2;
        if(!isLost){
        knife.style.top=topInc+"px";
        info.innerHTML="Place Your Finger Until Blade don't move";}
        if(scoreInc&&!isLost){
            score+=10;
        scoreB.innerHTML=score;
        scoreInc=false;
        isFunRun=false;}
        else if(isFunRun==false){
        score-=5;
        scoreB.innerHTML=score;
        isFunRun=false;
        if(score<=-30){
            scoreOnB.innerHTML="Score Acheive: "+score;
               sBoard.style.display="block";
            userLoseInfo.innerHTML="Due to Continous negative scoring You are disqualified ";
            userLoseInfo.style.fontSize="10px";
            document.getElementById('isLose').style.left="5px";
            document.getElementById('go').style.left="48px";
            }
          }
    }
    
 /* Function define To drop Blade when
  its Call */
  
    function knifeMove()
    {
       if(score>=45&&score<100){
           topInc+=3;
           
       }
       else if(score>=100){
           topInc+=4;
       }    
       else{
           topInc+=2;
       }
       knife.style.position='absolute';
       knife.style.top=topInc+"px";
        
       if(knife.style.top==251+"px"||knife.style.top==250+"px"){
            clearInterval(timeUp);
            isLost=true;
            finPos.style.background="radial-gradient(red,rgba(255,0,0,0.9),rgba(255,224,0,0.3),rgba(255,123,0,0.6))";
            finPos.style.border="solid rgba(255,224,0.7)";
            scoreOnB.innerHTML="Score Acheive: "+score;
           userLoseInfo.innerHTML="Blade Hit on Finger 😭";
           userLoseInfo.style.fontSize="17px";
            document.getElementById('isLose').style.left="32px";
            document.getElementById('go').style.left="25px"; 
            sBoard.style.display="block";
        }
       if(knife.style.top==10+'px'||knife.style.top==8+'px')
         scoreInc=true;
       isFunRun=true;      
    }
    
 /* retry Option in Game */
 
    function retry()
    {
        sBoard.style.display="none";
         knife.style.position="absolute";
        knife.style.top="2px";
        score=0;
        scoreB.innerHTML=score;
        isLost=false;
        finPos.style.background="repeating-radial-gradient(grey,black,rgba(0,0,0,0.1))";
        finPos.style.border="solid black"
        info.innerHTML="Place Your Finger Until Blade don't move";
        isFunRun=false;  
    }
  /* Function to take InPut */
  
  function input()
  {
      name=prompt("Enter Name Here","Carlo");
      if(name=="null"){
          name="Carlo";
      }
      inputI.innerHTML="Hi,"+name;
      inputI.style.color='aqua';
      inputI.style.letterSpacing="2px";
      quote.innerHTML=name+" ,Be Focus to Score High";
      report.innerHTML=name+" :";
  }
 /* Ending */

    </script>
    </body>
</html>
