# Build-A-Simple-Alarm-Clock
An alarm clock is created for user to set their alarm when needed. There are three main tools been used for this creation which are HTML, CSS and JavaScript. 
## HTML
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
In the HTML file, I included the content which will be shown on the website. The contents included an image of alarm, the time, the button to set and clear alarm.
## CSS
```
```
In the CSS file, I structure and style the content through margin, padding,box-sizing, alignement, font etc. 
## JavaScript
```
```
The element with functions like button and time are contained in this Javascript file. 


Now, the alarm clock is ready for your service!
