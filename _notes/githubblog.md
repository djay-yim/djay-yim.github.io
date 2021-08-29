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

## Github Blog 작성 Tips  
### ⭐ Notice
> {: notice--{level}}

\{: .notice\-\-info}<button class="copy">Copy</button>
{: .notice--info}

\{: .notice\-\-warning}<button class="copy">Copy</button>
{: .notice--warning}

\{: .notice\-\-success}<button class="copy">Copy</button>
{: .notice--success}

\{: .notice\-\-danger}<button class="copy">Copy</button>
{: .notice--danger}

---

### ⭐️ Link
> #### Url Link
```javascript
[link name](link 주소)
```

> #### 문서 내 Link
```javascript
[link name](#header name)
```

e.g.
- [url link](#url-link)
- [문서 내 link](#문서-내-link)
- [⭐️ 강조](#️-강조)

plain text 👇
```javascript
- [url link](#url-link)
- [문서 내 link](#문서-내-link)
- [⭐️ 강조](#️-강조)
```
        
**Please Note**   
→ "#" 이 여러개 여도 1개만 표기 e.g. (#url-link)  
→ 공백은 "-"로 e.g. (#문서-내-link)  
→ 영어는 소문자로 e.g. (#url-link)  
→ 특수문자는  무시 e.g. (#️-강조)  
{: .notice--danger}

---

<style>
.copy{float: right; background-color: #00adb5; color: white; font-weight: bolder;}
</style>

<script>

document.addEventListener("DOMContentLoaded", function(){

  $(".copy").bind("click", function(){
  
    var _this = $(this);
    var thisText = _this.text();
    var copyText = _this.parent().text().replace(thisText, '').trim();
    var tempElem = document.createElement('textarea');
    tempElem.value = copyText;  
    document.body.appendChild(tempElem);
  
    tempElem.select();
    document.execCommand("copy");
    document.body.removeChild(tempElem);

    _this.text("You've just gotten this word!");
  
    setTimeout(function() {
      _this.text("Copy");
    }, 700);
  });
});
</script>