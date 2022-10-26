# Build-A-Simple-Alarm-Clock
An alarm clock is created for user to set their alarm when needed. There are three main tools been used for this creation which are HTML, CSS and JavaScript. 
## HTML
In the HTML file, I included the content which will be shown on the website. The contents included an image of alarm, the time, the button to set and clear alarm.
```
<html>
<head>
    <meta charset="utf-8">
    <title>Alarm Clock  in JavaScript</title>
    <link rel="stylesheet" href="style.css">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
    <div class="wrapper">
        <img src="files/clock.svg" alt="clock">
        <h1>00:00:00 PM</h1>
        <div class="content">
            <div class="column">
                <select>
                    <option value="Hour">Hour</option>
                    
                </select>
            </div>
            <div class="column">
                <select>
                    <option value="Minute" selected hidden>Minute</option>
                  
                </select>
            </div>
            <div class="column">
                <select>
                    <option value="AM/PM" selected hidden>AM/PM</option>
                                 
                </select>
            </div>
        </div>
        <button>Set Alarm</button>
    </div>
    <script src="script.js"></script>
</body>
<html>
```
## CSS
In the CSS file, I structure and style the content through margin, padding,box-sizing, alignement, font etc. 
```
*{  
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: 'Poppins',sans-serif;
}

body,.wrapper, .content{
   display: flex; 
   align-items: center;
   justify-content:center;
}
body{
    min-height:100vh;
    background:#4a98f7
}
.wrapper{
    width:440px;
    background:#fff;
    border-radius:10px;
    flex-direction:column;
    padding:30px 30px 38px;
}
.wrapper img{
    max-width:103px;
}
.wrapper h1{
    font-size:30px;
    font-weight:500;
    margin:30px 0;
}
.wrapper .content{
width:100%;
justify-content:space-between;
}

.wrapper .content.disable{
    opacity:0.6;
    pointer-events:none;

}
.content.column{
    border-radius:5px;
    border:1px solid#999;
    width:calc(100%/3-5px);
}
.column select{
    outline:none;
    border:none;
    height:53px;
    width:100%;
    font-size:19px;
}
.wrapper button{
    width:100%;
    outline:none;
    border:none;
    cursor:pointer;
    color:#fff;
    margin-top:20px;
    font-size:20px;
    padding:17px 0;
    border-radius:5px;
    background:#4a98f7;
}
```
## JavaScript

The element with functions like button and time are contained in this Javascript file. 

```
const currentTime=document.querySelector("h1"),
content=document.querySelector(".content"),
selectMenu=document.querySelectorAll("select"),
setAlarmBtn=document.querySelector("button");

let alarmTime, isAlarmSet=false,
ringtone= new Audio("./files/ringtone.mp3");

for (let i=12;i>0;i--)
{
    i=i<10?"0"+1:i;
    let option= '<option value="${i}">${i}</option>  ';
    selectMenu[0].firstElementChild.insertAdjacentHTML("afterend",option);
}
for (let i=59;i>0;i--)
{
    i=i<10?"0"+1:i;
    let option= '<option value="${i}">${i}</option>  ';
    selectMenu[1].firstElementChild.insertAdjacentHTML("afterend",option);
}
for (let i=2;i>0;i--)
{
    let ampm= i==1?"AM":"PM";
    let option= '<option value="${ampm}">${ampm}</option>';
    selectMenu[2].firstElementChild.insertAdjacentHTML("afterend",option);
}

setInterval(()=>{
    //getting hour, mins, secs
    let date= new Date(),
    h=date.getHours(),
    m=date.getMinutes(),
    s=date.getSeconds(),
    ampm="AM"

    if(h>=12){
        h=h-12;
        ampm="PM";
    }
    //if hour value is 0, set this value to 12
    h=h==0? h=12:h;
    //adding 0 before hr, min, sec if this value is less than 10
    h=h<10?"0"+h:h;
    m=m<10?"0"+m:m;
    s=s<10?"0"+s:s;

    currentTime.innerText('${h}:${m}:${s} ${ampm}')

    if(alarmTime=="${h}:${m}:${s} ${ampm}")
    {
        ringtone.play();
        ringtone.loop=true;
    }

},1000)

function setAlarm(){
    if(isAlarmSet)
    {
        alarmTime=""; //if is AlarmSet is True
        ringtone.pause(); //clear the value of alarmTime
        content.classList.remove("disable"); //pause the ringtone
        setAlarmBtn.innerText="Set Alarm";
        return isAlarmSet=false; //return isAlarmSet value to false
    }

    //getting hour, minute,ampm select tag value
    let time="${selectMenu[0].value}:${selectMenu[1].value}:${selectMenu[2].value}";
    if(time.includes("Hour")||time.includes("Minute")||time.includes("AM/PM")){
        return alert("Please, select a valid time to set Alarm!");
    }
    isAlarmSet=true;
    alarmTime=time;
    content.classList.add("disable");
    setAlarmBtn.innerText="Clear Alarm";
}
setAlarmBtn.addEventListener("click",setAlarm);
```
Now, the alarm clock is ready for your service!
