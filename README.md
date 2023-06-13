# <!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="content-type" name="viewport" content="text/html; charset=utf-8;width=device-width, initial-scale=1.0" />
    <title>HCF</title>
    <style type="text/css" media="all">
    #HCF,#btn{
      border: none;
     background:linear-gradient(0deg,purple,pink);
     float:right;
       animation:input 4s linear 3 ;
    }  
    .input{
      border :dotted;
      width :105px;
      margin :0px 40px 5px 0px;
    }
    .input:focus{
      background: #edad5505;
      animation : input ease-out  6s infinite;
    }
    @keyframes input{
      0%{box-shadow:pink 0px 0px 0px;}
      20%{box-shadow:pink 0px 0px 10px;}
      40%{box-shadow:pink 0px 0px 0px;}
      60%{box-shadow:purple 0px 0px 0px;}
      80%{box-shadow:purple 0px 0px 10px;}
      100%{box-shadow:purple 0px 0px 0px;}
    }
    </style>
  </head>
  <body>
    <p>Click on + icon. Enter your number A1 A2 A3 A4 ... An. Click on HCF .</p>
    <input type="button" name="" id="btn" onclick="clicked()" value="+" />
    <div id="div">
      
    </div>
    <input type="button" name="HCF" id="HCF" onclick="hcf()" value="HCF" />
    <script type="text/javascript" charset="utf-8">
    var m = [];//for storing i's
    var g = [];
    var finalNumber = [];
    var realNumuber = [];
    var i;//for id input 
    var n = 1;//for id
    var test = true;
    var div = document.getElementById("div");
    
     function clicked(){
       i = String("a"+n) ;
       g.push(i);
       let input = document.createElement("input");
       input.setAttribute("type","number");
       input.setAttribute("class","input");
       input.setAttribute("id",i);
     div.appendChild(input);
      n++;
     }
     
     
    function hcf(){
      for(let randomNumber in g){
        m.push(document.getElementById(g[randomNumber]).value);
    }
       for(let randomNumber in m){
        if (m[randomNumber]==""){
          alert(`Your ${randomNumber} block is empty!`);
        }else if(m[randomNumber]=="0"){
          document.write(0)
          break;
        } else {
         realNumuber.push(Number(m[randomNumber]));
       }
       }
       var finalNumber = realNumuber.sort(function(a,b){return b-a});
      document.write(answer(finalNumber));//answer here ! 
     }
     
 function answer(){
       var bool = true ;
       if(bool == true){
         var a = realNumuber[0];
         var b = realNumuber[1];
         var r ;
         ra();
         function ra(){
           r = a % b ;
           a = b ;
           b = r ;
           if(r!=0){
             ra();
           bool = false;
           return a;
         }
         if(bool==false&&realNumuber.length<2){
           for(let j = 2 ; j<realNumuber.length;j++){
            find(a,realNumuber[j]);
           }
         }
       }
     }
     return a;
     }
     function find(a,b){
       let f = a % l ;
           k = l ;
           l = f ;
           if(f!=0){
             find(k,l);
           bool = false;
           return a;
     }
     }
    </script>
  </body>
</html>
