# JS-game
A fun, and a simple game, with some few lines of HTML, CSS and JS code. The game would consist of a block and a character, if the character hits the block you lose, if you jump over the character, you score. Hoping the idea is crystal clear to everyone, let’s build it!
To explain the above code, in simplest terms, the key role is being played by JS, however, we utilize CSS to create some interesting animations. To understand, we have created our character, by defining its dimensions, and the same goes for the block, and the block moves towards the character as evident by the GME.CSS code. Also, since we need the character to jump, and stay a bit and then come back to the ground, we have created two animations for the same, in the CSS file. First animation is for the block, where we use it to move the block through the screen, and similarly for the character jumps we create an animation, and add the respective classes to “animation”.

Now we need to add and remove animation class, in order to jump everytime, this is done by:

function jump(){
if(character.classList == "animate"){return}
character.classList.add("animate");
setTimeout(function(){
character.classList.remove("animate");
},300);
}
The last thing that needs to be detected is the hit, for this we check the top position of the character and the lefty position of the block and compare them against each other, if they seem inside each other that implies that they have hit. This is decided by the below snippet:

var checkDead = setInterval(function() {
let characterTop = parseInt(window.getComputedStyle(character).getPropertyValue("top"));
let blockLeft = parseInt(window.getComputedStyle(block).getPropertyValue("left"));
if(blockLeft<20 && blockLeft>-20 && characterTop>=130){
block.style.animation = "none";
alert("Game Over. score: "+Math.floor(counter/100));
counter=0;
block.style.animation = "block 1s infinite linear";
}else{
counter++;
document.getElementById("scoreSpan").innerHTML = Math.floor(counter/100);
}
}, 10);
And THAT IS IT!


HOPE YOU ENJOYED!
