---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Parsons Practice

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "import random \n" +
    "lost = False \nscore = 0 \n" +
    "print(&quot;Welcome to Twisted Guess the Number!&quot;) \nprint(&quot;You&#039;ll be presented with two numbers and asked to guess the third,&quot;) \nprint(&quot;which will either be the sum of the two,&quot;) \nprint(&quot;the multiple of the two,&quot;) \nprint(&quot;or the second subtracted from the first.&quot;) \n" +
    "while not lost: \n" +
    "    number1 = random.randint(1, 11) \nnumber2 = random.randint(1, 11) \noption = random.randint(1, 3) \n" +
    "    if option == 1: \n" +
    "        answer = number1 + number2 \n" +
    "    elif option == 2: \n" +
    "        answer = number1 - number2 \n" +
    "    else: \n" +
    "        answer = number1 * number2 \n" +
    "    print(&quot;The first number is:&quot;, number1) \nprint(&quot;The second number is:&quot;, number2) \n" +
    "    guess = int(input(&quot;Take a guess at the third number: &quot;)) \n" +
    "    if guess == answer: \n" +
    "        score += 1 \nprint(&quot;You were right! Your score is now:&quot;, score) \n" +
    "    else: \n" +
    "        print(&quot;Incorrect! The answer was actually:&quot;, answer) \nprint(&quot;Your final score is:&quot;, score) \nlost = True \nprint() \n";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "sortableTrash"
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
})(); 
</script>
### Implementation Notes

When you host multiple Parson's problems on a single markdown page, you need to add a unique prefix. You can easily do this in the Codio generator by typing a unique prefix into the "Prefix" textbox and pressing Enter/Return. Then you can simply copy-paste like normal.

If want each problem to be it's own page, you can use relative path links at the bottom of each of your markdown pages as seen below. If you want students to be able to return to previous problems in this format, consider adding previous links or link to a table of contents like page.

### Example Next Link
[Next](./parsons/example1.html)
