---
layout: default
title: Santa Speed Function (Parsons Puzzle)
---

# Santa Speed Function

Reorder the lines of code so the program defines a function to calculate how fast Santa’s sleigh travels.
Each reindeer adds **150 mph**.

<div id="sortableTrash" class="sortable-code"></div>
<div id="sortable" class="sortable-code"></div>
<div style="clear:both;"></div>

<p>
  <input id="feedbackLink" value="Get Feedback" type="button" />
  <input id="newInstanceLink" value="Reset" type="button" />
</p>

<script>
var initial =
"def calculate_speed(reindeer_count):\n" +
"    speed = reindeer_count * 150\n" +
"    return speed\n" +
"\n" +
"reindeers = int(input('How many reindeer are pulling the sleigh? '))\n" +
"speed = calculate_speed(reindeers)\n" +
"print('With', reindeers, 'reindeer, your speed is', speed, 'mph')\n";

var puzzle = new ParsonsWidget({
    sortableId: 'sortable',
    max_wrong_lines: 0,
    grader: ParsonsWidget._graders.LineBasedGrader,
    can_indent: true,
    x_indent: 50
});
puzzle.init(initial);
puzzle.shuffleLines();

document.getElementById("newInstanceLink").onclick = function(e){
  e.preventDefault();
  puzzle.shuffleLines();
};

document.getElementById("feedbackLink").onclick = function(e){
  e.preventDefault();
  alert(puzzle.getFeedback().feedback);
};
</script>
