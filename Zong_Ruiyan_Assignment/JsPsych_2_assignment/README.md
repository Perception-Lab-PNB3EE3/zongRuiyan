# Manually create a blue square image because I looked up online and 
# only found methods o turn square image into circle, but no result 
# that turns circle into square.

# Modified the instruction:
<div style='float: left;'><img src='img/blue_square.png' style='width: 50%;'></img>

# Make the orange image half diameter by defining the width to be 50%:
<div style='float: right;'><img src='img/orange.png' style='width: 50%;'></img> 

# At the end of the experiment, add feedback regarding how fast participants’ reaction times were for the blue squares vs. orange circles.
# By filter the trials for each stimuli and select their reaction times and then calculate average.

var blue_rt = Math.round(trials.filter({stimulus:'img/blue_square.png'}).select('rt').mean());
var orange_rt = Math.round(trials.filter({stimulus:'img/orange.png'}).select('rt').mean())


<p>Your average response time for blue squares was ${blue_rt}ms.</p>

<p>Your average response time for orange circles was ${orange_rt}ms.</p>