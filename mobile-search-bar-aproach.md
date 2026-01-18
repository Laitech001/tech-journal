## The problem: the search button is working on desktop but not working on mobile devices

## what cause the problem is that, in my js file, I only call a sinlge seaarch input and the button while it is not one, the search bar and the its button have the class name for both desktop and mobile and they are like a list of array so we can just call the button and the search bar directly.

## Solution 
I see the search bar and the button as a list of array, and to select a list of array, we can you querySelectorAll('.');
I use this method to call all the search bar and button with the same class in my code and it work.
