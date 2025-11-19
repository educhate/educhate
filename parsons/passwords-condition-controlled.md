---
layout: default
title: "Password Checker: Conditional Controlled"
---

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 

<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<p class="task-description">
An algorithm is used to ensure a password is at least 7 characters in length. The user is repeatedly asked to enter a password until it is longer than 7 characters.​

A counter is used to count how many attempts it took to create a "strong" password. The counter and allowed password is outputted
</p> 
<script type="text/javascript">
var initial = "length = 0\n" +
    "count = 0\n" +
    "while length &lt; 7:\n" +
    "  password = input(&quot;What is the password? &quot;)\n" +
    "  length = len(password)\n" +
    "  count = count + 1\n" +
    "print(&quot;It took &quot; + str(count) + &quot; attempts&quot;)";
    
var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true
});
parsonsPuzzle.init(initial);
parsonsPuzzle.shuffleLines();

$("#newInstanceLink").click(function(event){ 
    event.preventDefault(); 
    parsonsPuzzle.shuffleLines(); 
}); 

$("#feedbackLink").click(function(event){ 
    event.preventDefault(); 
    parsonsPuzzle.getFeedback(); 
}); 
</script>

