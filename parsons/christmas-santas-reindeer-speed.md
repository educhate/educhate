---
layout: default
title: "Christmas: Santa's Reindeer Speed"
---

# 🎄 Santa's Reindeer Speed

Reorder the lines so the program uses a function to calculate Santa’s sleigh speed.
Each reindeer adds **150 mph**.

<div id="sortableTrash" class="sortable-code"></div>
<div id="sortable" class="sortable-code"></div>
<div style="clear:both;"></div>

<p>
  <input id="feedbackLink" value="Get Feedback" type="button" />
  <input id="newInstanceLink" value="Reset" type="button" />
</p>

<script type="text/javascript">
(function(){
  var initial =
"def calculate_speed(reindeer):\n" +
"    speed = reindeer * 150\n" +
"    return speed\n" +
"\n" +
"count = int(input('How many reindeer are pulling the sleigh? '))\n" +
"mph = calculate_speed(count)\n" +
"print('Your sleigh speed is', mph, 'mph')\n";

  var parsonsPuzzle = new ParsonsWidget({
      sortableId: 'sortable',
      max_wrong_lines: 0,
      grader: ParsonsWidget._graders.LineBasedGrader,
      exec_limit: 2500,
      can_indent: true,
      x_indent: 50,
      lang: 'en'
  });

  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();

  $("#newInstanceLink").click(function(e){
      e.preventDefault();
      parsonsPuzzle.shuffleLines();
  });

  $("#feedbackLink").click(function(e){
      e.preventDefault();
      var feedback = parsonsPuzzle.getFeedback();
      alert(feedback.feedback);
  });
})();
</script>
