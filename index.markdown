<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "schools = [&quot;Naperville Central&quot;, &quot;Naperville North&quot;, &quot;Neuqua Valley&quot;, &quot;Metea Valley&quot;, &quot;Waubonsie Valley&quot;]\n" +
    "d203Schools = []\n" +
    "for school in schools:\n" +
    "	if &quot;Naperville&quot; in school:\n" +
    "    	d203Schools.append(school)\n" +
    "        \n" +
    "print(&quot;Schools in Naperville CUSD 203:&quot;)\n" +
    "print(d203Schools)";
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
})(); 
</script>
