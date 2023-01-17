# Day 4 11-01-23

# Problem

## <a href="https://github.com/sohrabhamza/Days-of-code-JS/tree/main/Day%204">Code</a> & <a href="https://www.linkedin.com/posts/sohrab-hamza-ab13151a5_vitbhopalgaming-daysofcode-day4-activity-7019156166026932224-Vi6f?utm_source=share&utm_medium=member_desktop">Post</a>

Create a simple hangman game. The program will show the amount of letters in the word. User can enter one letter at a time. If It is the correct letter, all blanks ("\_") corresponding to that letter will be filled in. If not then a new body part of the hangman will be drawn. If all letters are guessed before the man is hanged, then you win. Else you lose. 

```js
function HangCheck(x) {
            //If all hangman parts have been drawn, you lose. 
            if (currentIm === hangIms.length - 1) {
                document.getElementById("Win").textContent = "You Lose";
                return;
            }

            //Check if the displayed text is changed.
            let changed = false;

            //Check if inputted letter is present in parent letter and change the text on screen
            for (let i = 0; i < hangVars[currentIndex].length; i++) {
                if (hangVars[currentIndex].charAt(i) === x) {
                    textToShow = textToShow.replaceAt(i * 2, x + " ");
                    changed = true;
                    alert(textToShow);
                }
            }
            document.getElementById("HangText").textContent = textToShow;
            document.forms["Hang"]["tIn"].value = "";

            //If not changed, hang the man
            if (!changed) {
                currentIm += 1;
                document.getElementById("hangIm").src = "Img/" + (currentIm + 1) + ".png";
            }

            //If all blanks are filled, you win
            for (let i = 0; i < textToShow.length; i++) {
                if (textToShow.charAt(i) === "_") {
                    return;
                }
            }
            document.getElementById("Win").textContent = "You Win";
        }
```

<img src="https://i.imgur.com/QjitaXT.png" title="" alt="" width="397">

# Tests

Check wrong input:

> New part of the hangman is drawn. 

Check correct input:

> Blank is filled in.

# Improvements

Validation for the input given. 

- Remove everything that is not a letter

- Convert to upper case

- Call HangCheck() multiple times if a string is inputted

Auto update on win and lose. 
