---
title: "PlayToonPlayer Launcher"
categories:
  - PlayToon
tags:  
  - playtoon
  - player
  - launcher
toc: true
---

# PlayToonPlayer
<!-- Html 문법과 markdown 문법 섞임 -->
**Watch out!** This is the PlayToonPlayer Launcher page. [PlayToonPlayer](#playtoonplayer).
{: .notice--warning}

<!-- <form id="formTargetRadio">
  <fieldset>
    <p>Only QA can be selected:</p>
    <div>
      <input type="radio" id="Develop" name="contact" value="Develop" disabled> Develop
      <label for="Develop"></label>
      <input type="radio" id="Test" name="contact" value="Test" disabled> Test
      <label for="Test"></label>
      <input type="radio" id="QA" name="contact" value="QA" checked> QA
      <label for="QA"></label>
      <input type="radio" id="Real" name="contact" value="Real" disabled> Real
      <label for="Real" ></label>
    </div>
  </fieldset>
</form> -->

<form id="formInputInfo" action="javascript:;" onsubmit="return PlayToonSubmit(this);">
    <input id="title" type="text" placeholder="Title" list="title-list" required />
    <datalist id="title-list">
        <option value="Title_Sample"></option>
    </datalist>
    <input id="episode" type="text" placeholder="Episode" list="episode-list" required />
    <datalist id="episode-list">
        <option value="Episode1"></option>
    </datalist>
    <input id="token" type="text" placeholder="Tokens issued by the platform" list="token-list" required />
    <datalist id="token-list">
        <!-- <option value="2Q+XL16sTtE="></option> -->
    </datalist>
    <button type="submit" id="show-selected" class="btn btn--info">Play</button>
</form>

<script charset="UTF-8" type="text/javascript">
  String.prototype.format = function() {
    var formatted = this;
    for (var i = 0; i < arguments.length; i++) {
        var regexp = new RegExp('\\{'+i+'\\}', 'gi');
        formatted = formatted.replace(regexp, arguments[i]);
    }
    return formatted;
  }
  function PlayToonSubmit(theForm){
    let playerRootUrl = "{{site.data.playtoon-urls.player.root}}";
    let token = theForm.elements["token"].value;
    let title = theForm.elements["title"].value;
    let episode = theForm.elements["episode"].value;
    // for(let i=1; i < formTargetRadio.elements.length; ++i){
    //   if(formTargetRadio.elements[i].checked){
    //     var target = formTargetRadio.elements[i].value;
    //   }
    // }
    var url = "{0}/QA/Player/index.html?token={1}?title={2}?episode={3}".format(playerRootUrl, token, title, episode);
    location.href=url;
  }
</script>
