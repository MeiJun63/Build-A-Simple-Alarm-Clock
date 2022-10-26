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
```
```
The element with functions like button and time are contained in this Javascript file. 


Now, the alarm clock is ready for your service!
