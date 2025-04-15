---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Parsons Practice

## Recursive fibonacci
Rearrange the code fragments to a function calculating the n:th Fibonacci number!

<div id="fibonacci-sortableTrash" class="sortable-code"></div> 
<div id="fibonacci-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="fibonacci-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="fibonacci-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "def fib(n):\n" +
    "	if n == 1 or n == 2:\n" +
    "    	return 1\n" +
    "    else:\n" +
    "    	return fib (n-1)+ fib(n-2)\n" +
    "return 2 #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "fibonacci-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "fibonacci-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#fibonacci-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#fibonacci-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>

## Recursive fibonacci sequence calculation with memoization
Re-arrange the blocks below so they memoize the calculation of the n:th Fibonacci number!

<div id="memoFibonacci-sortableTrash" class="sortable-code"></div> 
<div id="memoFibonacci-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="memoFibonacci-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="memoFibonacci-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "memo = [None]*(n+1)\n" +
    "def fib(n):\n" +
    "	if memo[n] is not None:\n" +
    "    	return memo[n]\n" +
    "    if n == 1 or n == 2:\n" +
    "    	memo[n] = 1\n" +
    "    else:\n" +
    "        memo[n] = fib(n-1) + fib(n-2)\n" +
    "    return memo[n]\n" +
    "return 1 #distractor\n" +
    "memo[n] += 1 #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "memoFibonacci-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "memoFibonacci-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#memoFibonacci-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#memoFibonacci-feedbackLink").click(function(event){ 
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
