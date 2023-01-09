# Day 2 09-01-23

# Problem

Improving upon yesterdays work with regex, multiple pages and external stylesheets. 

We have two linked pages. One a home page for a chess club. The second a sign up page. 

In the sign up page, we have a name field, a roll number field (VIT Roll) and a checkbox. 

Name cannot have anything other than letters. Regex:

`/[^a-zA-Z ]+/`

Roll number should be of format 19, 20 or 21 + B + G/E/Y + any 5 numbers. Regex:

`/(19|2[0-3])BC[GEY]\d{5}/`



# Higlighted Code

```js
function formValidate() {
            let rollV = false, enthuV = false, nameV = false; //Variables for checks
            let roll = document.forms["memberForm"]["froll"].value; //Get rollnumber
            let name = document.forms["memberForm"]["fname"].value; //Get name
            let rollgex = /(19|2[0-3])BC[GEY]\d{5}/     //Regex for roll number

            let alertNew = "";      //Declare string for alerts

            //Checks for each field. If passed then set that check's bool to true, else concat an error message
            if (name.match(/[^a-zA-Z ]+/) != null) {
                alertNew += "Your name cannot contain anything except letters \n";
            }
            else {
                nameV = true;
            }

            if (roll.match(rollgex) == null || roll == "") {
                alertNew += roll == "" ? "Roll number empty \n" : "Invalid Roll Number \n";
            }
            else {
                rollV = true;
            }

            if (document.getElementById('fenthu').checked == false) {
                alertNew += "Please be enthusiastic \n";
            }
            else {
                enthuV = true;
            }

            //If there are alerts, alert
            if (alertNew != "") { alert(alertNew); }
            
            //If all checks passed, thank user
            if (rollV && enthuV && nameV) { window.location.href = "index.html"; alert("Thank you for registering"); }
            else { return true }
        }
```

# Tests:

**If name has anything other than letters:**

> Error: Your name cannot contain anything other than letters and spaces. 

- Invalid syntax: `Sohrab 2`, `So$rab`, etc

- Valid: `Sohrab Hamza`

**If roll number is not in format:**

> Error: Please enter valid roll number

- Invalid syntax: `21BCC1012`

- Valid Syntax: `21BCG10051`

**If checkbox is not checked:**

> Error: Please be enthusiastic.



# Improvements

Auto removal of special characters in the name field. 

Minimum name size requirements








