# Day 3 10-01-23

# Problem
## <a href="https://github.com/sohrabhamza/Days-of-code-JS/tree/main/Day%203">Code</a> & <a href="https://www.linkedin.com/posts/sohrab-hamza-ab13151a5_vitbhopalgaming-daysofcode-day3-activity-7018641626986115073-m9mP?utm_source=share&utm_medium=member_desktop">Post</a>

Creating a simple rgb to hex converter page which then displays the color as the background of the page. 

```js
function componentToHex(c) {
            var hex = c.toString(16);       //Converts to hex  
            return hex.length == 1 ? "0" + hex : hex;    //0 in front if too short
        }

        function rgbToHex(r, g, b) {
            //Converts each component to hex
            return "#" + componentToHex(r) + componentToHex(g) + componentToHex(b);
        }
```

Then we simply have a form to collect the r, g and b values and convert them and set them to the page color. Also is displayed at the bottom

```js
document.getElementById("Background").style.background = hex;
document.getElementById("text").textContent = hex;
```

<img title="" src="https://i.imgur.com/aACugOn.png" alt="" href="https://i.imgur.com/aACugOn.png" width="351">

# 

# Tests

Check several colors: Desired output.

Empty: No error and nothing happens. 

# Improvements

Could consolidate multiple r g and b input boxes to one and process the data to extract individual components. 
