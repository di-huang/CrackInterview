
Save the (start, end) indices of a-z letters in the string; <br />
<br />
For c = 1st letter in loop { <br />
Get the (start, end) indices of c; <br />
From start to end, make sure that each letter only appears in the current part, otherwise, we extend this part until the above condition is met; <br />
Record the size of this part; <br />
}