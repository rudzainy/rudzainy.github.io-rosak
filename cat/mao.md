---
layout: page
title: The Door
sitemap: false
---
<div id="box">
	<p>What is a four-letter word that has only one vowel in it.</p>
  <form>
    <label for="answer">Answer</label>
    <input type="password" name="answer" />
    <button type="submit">Submit answer</button>
  </form>
</div>
<script>
  const ansArray = ["true","correct","ya","betul","yes","yup","yups","👍"]
  let queryString = window.location.search
  // alert("queryString = \"" + queryString + "\"")
  const ansRegex = /[^\?answer=]/
  if(ansRegex.test(queryString)) {
    let ans = queryString.substr(queryString.indexOf("=") + 1)
    // alert("ans = \"" + ans + "\"")
    if(ansArray.includes(ans.toLowerCase())) {
      let box = document.getElementById('box')
      box.innerHTML = "👀<br /><ol><li><a href='#'>Link 1</a></li><li><a href='#'>Link 1</a></li></ol>"
    }
  }
</script>