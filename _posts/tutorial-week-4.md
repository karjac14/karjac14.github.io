
_Edit: This tutorial is an explanation of what I did learned in Week 4 Chessboard assignement. With chess 2.0 came in this week, that has more emphasized requirements and starting points, some parts may not be relevant for chess 2.0.

From the last week's assignemnt, I learned how to link the three parts of the MVC, (well, what I think it should be) I will recap how the three were linked, some invocations, and return values in the Chessboard assignment. There may be more ways of doing these linkages between the M, V and C, but I will show below how I demonstrated them:

####View to Controller

 - Properly identify the elements to be used in the html and assign classes and ids.
 - Properly link the .js files (main.js first, and then controller.js) and css file(s). The html files serves as a hub for all the needed files to be linked.
 - Using Jquery or JS,  controller listens to any user actions such as "click". 
 
      `jQuery('#forward').on('click', function(event){});`
 
####Controller to Model
 
 - When the controller detects the user interaction, it invokes a specific method in the main.js
 
      `game.next();`
 
####Model to Controller

 - When the methods in the main.js are invoked, it executes the statements and operations inside of the block operator. Below is an example of the statements that are executed.
 
```
      if (ctr < moves.length) {
      ctr += 1;
      console.log (ctr);
      game.applyMove(true,false); 
```
      
 - Remember that controller.js depends on the main.js, and not the other way around. In main.js we can't invoked anything in the controller.js. The model ussually holds database and performs operations internally.
 
 - To get the return value of the methods in main.js,  I assigned the return value of the invoked method to a variable.
 
       `game.next();`  to --->   `var arr = game.next();`
       
       In this way, the return value of `game.next();` will be assigned to identifier `arr`. Doing so, we were able to close the link between model and controller.  
 
 
####Conroller to View
 
 - From the data that we got from the model, we use Jquery again to change, add, or remove classes of the our DOM elements. From there we can alter the behaviour of the html elements. 
 
     `$('#F6').addClass('bknight');
      $('#G8').removeClass('bknight');`
 
- Surely, there are more ways of linking the MVC architecture and hopefully we can learn them further through more practice.
