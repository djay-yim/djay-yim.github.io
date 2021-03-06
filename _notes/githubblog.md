---
title: "Github Blog"
permalink: /notes/githubblog/
toc: true
toc_sticky: true
categories:
  - notes 
tags:
  - tips
---

## Github Blog μμ± Tips  
### β­ Notice
> {: notice--{level}}

\{: .notice\-\-info}<a href="#this" style="color: white; float: right;" class="copy btn btn--info">Copy? π</a>
{: .notice--info}

\{: .notice\-\-warning}<a href="#this" style="color: white; float: right;" class="copy btn btn--warning">Copy? π</a>
{: .notice--warning}

\{: .notice\-\-success}<a href="#this" style="color: white; float: right;" class="copy btn btn--success">Copy? π</a>
{: .notice--success}

\{: .notice\-\-danger}<a href="#this" style="color: white; float: right;" class="copy btn btn--danger">Copy? π</a>
{: .notice--danger}

---

### β­ Table
> Table <a href="#this" id="AnchorTableCopy" class="btn">Copy? π</a> 

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}


---

### β­οΈ Link
> #### Url Link
```javascript
[link name](link μ£Όμ)
```

> #### λ¬Έμ λ΄ Link
```javascript
[link name](#header name)
```

e.g.
- [url link](#url-link)
- [λ¬Έμ λ΄ link](#λ¬Έμ-λ΄-link)
- [β­οΈ κ°μ‘°](#οΈ-κ°μ‘°)

plain text π
```javascript
- [url link](#url-link)
- [λ¬Έμ λ΄ link](#λ¬Έμ-λ΄-link)
- [β­οΈ κ°μ‘°](#οΈ-κ°μ‘°)
```
        
**<span style="color: #d67f05;">Please</span> Note π**   
β "#" μ΄ μ¬λ¬κ° μ¬λ 1κ°λ§ νκΈ° e.g. (#url-link)  
β κ³΅λ°±μ "-"λ‘ e.g. (#λ¬Έμ-λ΄-link)  
β μμ΄λ μλ¬Έμλ‘ e.g. (#url-link)  
β νΉμλ¬Έμλ  λ¬΄μ e.g. (#οΈ-κ°μ‘°)  
{: .notice--danger}

---

<style>
.copy{float: right; background-color: #00adb5; color: white; font-weight: bolder;}

.arrow_box {
  display: block;
  position: absolute;
  width: 70px;
  text-align: center;
  padding: 8px;
  left: 55px;
  -webkit-border-radius: 8px;
  -moz-border-radius: 8px;  
  border-radius: 8px;
  background: #333;
  color: #fff;
  font-size: 14px;
}

.arrow_box:after {
  position: absolute;
  bottom: 100%;
  left: 50%;
  width: 0;
  height: 0;
  margin-left: -10px;
  border: solid transparent;
  border-color: rgba(51, 51, 51, 0);
  border-bottom-color: #333;
  border-width: 10px;
  pointer-events: none;
  content: " ";
}

</style>

<script>

document.addEventListener("DOMContentLoaded", function(){

  $(".copy").bind("click", function(e){
  
    let _this = $(this);
    let thisText = _this.text();
    let copyText = _this.parent().text().replace(thisText, '').trim();

    copyTextToClipBoard(copyText);
    printTextAfterCopy(e);

  });
  
  $("#AnchorTableCopy").bind("click", function(e){
    
    let copyText = "";
    copyText += "| Header1 | Header2 |";
    copyText += "\n";
    copyText += "|:-------:|:-------:|";
    copyText += "\n";
    copyText += "| cell1   | cell2   |";

    copyTextToClipBoard(copyText);
    printTextAfterCopy(e);

  });

  const copyTextToClipBoard = function(sourceText){
    let tempElem = document.createElement('textarea');
    tempElem.value = sourceText;
    document.body.appendChild(tempElem);
    tempElem.select();
    document.execCommand("copy");
    document.body.removeChild(tempElem);
  };

  const printTextAfterCopy = function(e){
    let x = (e.pageX - 33) + "px";
    let y = e.pageY + "px";
    let floatObj = '<p class="arrow_box" style="left:'+x+'; top: '+y+'">Copied!</p>';
    $("body").append(floatObj);
    setTimeout(function() {
       $(".arrow_box").remove();
    }, 700);
  }

});
</script>