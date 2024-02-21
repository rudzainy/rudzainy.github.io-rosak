---
layout: page
title: The Door
---
<div id="box">
	<p>What is a four-letter word that has only one vowel in it.</p>
  <form action="/cat/mao" onSubmit="event.preventDefault(); hackering()">
    <label for="answer">Answer</label>
    <input type="password" name="answer" id="answer" />
    <button type="submit">Submit answer</button>
  </form>
</div>
<script>
  const ansArray = ["true","correct","ya","betul","yes","yup","yups","tepat","right","y","t","1"];
  let hackering = () => {
    jawaban = document.getElementById("answer").value;
    console.log(jawaban);
    if(ansArray.includes(jawaban.toLowerCase())) {
      const title = "The Door <i>is Opened!</i>";
      let webTitle = document.getElementsByClassName('dynamic-title')[0];
      let mobileTitle = document.getElementById('topbar-title');
      webTitle.innerHTML = title;
      mobileTitle.innerHTML = title;
      let box = document.getElementById('box');
      box.innerHTML = "Congrtulations code breaker person! 👀<br />Here are some goodies for you:<br /><ol><li><a href='https://www.rudzainy.my/assets/Portfolio_Rudzainy.pdf'>Portfolio (PDF)</a></li><li>Unlisted YouTube videos:<ul><li><a href='https://youtu.be/haeEC00aPTM'>Maya x Rudzainy Solemnization</a></li><li><a href='https://youtu.be/VVevtD-_F8Y'>Test link</a></li></ul></li><li><a href='https://rudzainy.blogspot.com/'>Old blog</a></li></ol><br /><h2>Draft posts</h2><ul><li><a href='/posts/rails-7-dropdown-image'>1</a></li><li>2</li><li>3</li><li>4</li></ul>";
    };
  };
</script>
