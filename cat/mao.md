---
layout: page
title: The Door
---
<div id="box">
	<p>What is a four-letter word that has only one vowel in it.</p>
  <form>
    <label for="answer">Answer</label>
    <input type="password" name="answer" />
    <button type="submit">Submit</button>
  </form>
</div>
<script>
var firstTimeUrl = document.URL;
  document.addEventListener('change', function() {
  var currentPageUrl = document.URL;
  var url = new URL(currentPageUrl);
  var isVariantUrl = url.searchParams.get("answer");
  currentPageUrl = isVariantUrl ? currentPageUrl :isVariantUrl;
    if(currentPageUrl && firstTimeUrl != currentPageUrl) {
      firstTimeUrl = currentPageUrl;
      alert('variant_id: '+isVariantUrl+'')
    }
  });

  const ansArray = ["true","correct","ya","betul","yes","yup","yups","👍"]
  const queryString = window.location.search
  console.log("queryString = \"" + queryString + "\"")
  const ansRegex = /[^\?answer=]/
  if(ansRegex.test(queryString)) {
    const ans = queryString.substr(queryString.indexOf("=") + 1);
    console.log("ans = \"" + ans + "\"")
    if(ansArray.includes(ans.toLowerCase())) {
      const box = document.getElementById('box')
      box.innerHTML = "👀<br /><ol><li><a href='#'>Link 1</a></li><li><a href='#'>Link 1</a></li></ol>"
    }
  }
</script>