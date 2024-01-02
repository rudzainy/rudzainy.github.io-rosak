---
layout: page
title: The Lock
---
<div id="door">
	<p>What is a four-letter word that has only one vowel in it.</p>
  <form hx-get="/cat/mekk" hx-target="🏴‍☠️" hx-trigger="submit">
    <!-- HTMX is not doing what I want... -->
    <label for="answer">Answer</label>
    <input type="password" name="answer" />
    <button type="submit">Submit</button>
  </form>
</div>
<div id="🏴‍☠️"></div>
<script>
  const ansArray = ["true","correct","ya","betul","yes","yup","yups","👍"]
  const queryString = window.location.search
  alert("queryString = \"" + queryString + "\"")
  const ansRegex = /[^\?answer=]/
  if(ansRegex.test(queryString)) {
    const ans = queryString.substr(queryString.indexOf("=") + 1);
    alert("ans = \"" + ans + "\"")
    if(ansArray.includes(ans.toLowerCase())) {
      const box = document.getElementById('box')
      box.innerHTML = "👀<br /><ol><li><a href='#'>Link 1</a></li><li><a href='#'>Link 1</a></li></ol>"
    }
  }
</script>