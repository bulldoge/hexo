# MathJax 配置文件

```

<!-- MathJax 2.7.1配置文件 -->
<!-- MathJax配置，可通过单美元符号书写行内公式等 -->
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    "HTML-CSS": {
      preferredFont: "TeX",
      availableFonts: ["STIX","TeX"],
      linebreaks: { automatic:true },
      EqnChunk: (MathJax.Hub.Browser.isMobile ? 10 : 50)
    },
    tex2jax: {
      inlineMath: [ ["$", "$"], ["\\(","\\)"] ],
      processEscapes: true,
      ignoreClass: "tex2jax_ignore|dno",
      skipTags: ['script', 'noscript', 'style', 'textarea', 'pre', 'code']
    },
    TeX: {
      equationNumbers: { autoNumber: "AMS" },
      noUndefined: { attributes: { mathcolor: "red", mathbackground: "#FFEEEE", mathsize: "90%" } },
      Macros: { href: "{}" }
    },
    messageStyle: "none"
  });
</script>
<!-- 给MathJax元素添加has-jax class -->
<script type="text/x-mathjax-config">
  MathJax.Hub.Queue(function() {
    var all = MathJax.Hub.getAllJax(), i;
    for(i=0; i < all.length; i += 1) {
      all[i].SourceElement().parentNode.className += (all[i].SourceElement().parentNode.className ? ' ' : '') + 'has-jax';
    }
  });
</script>
<!-- 通过连接CDN加载MathJax的js代码 -->
<!--可用：https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML-->
<!--待升级：https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.2/es5/tex-mml-chtml.min.js-->
<!--不起作用：/cdn/MathJax.js-->
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

```

```
<!-- MathJax 3.2.2配置文件 -->
<script>
  window.MathJax = {
    tex: {
      inlineMath: [ ["$", "$"], ["\\(","\\)"] ],
      processEscapes: true,
      tags: "ams",
      noundefined: {
        color: "red",
        background: "#FFEEEE",
        size: "90%"
      },
      macros: {
        href: "{}"
      },
      autoload: {
        color: [],
        colorv2: ['color']
      },
      packages: {'[+]': ['noerrors']}
    },
    options: {
      ignoreHtmlClass: "tex2jax_ignore|dno",
      skipHtmlTags: ['script', 'noscript', 'style', 'textarea', 'pre', 'code'],
      processHtmlClass: 'tex2jax_process'
    },
    loader: {
      load: ['input/asciimath', '[tex]/noerrors']
    }
  };
  </script>
  <!--可用，且快 https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.2/es5/tex-mml-chtml.min.js-->
  <!--可用，但慢 https://cdn.jsdelivr.net/npm/mathjax@3.2.2/es5/tex-mml-chtml.js-->
  <!--不可用，会报Nunjucks错误 cdn/mathjax/tex-mml-chtml.js-->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.2/es5/tex-mml-chtml.min.js" id="MathJax-script"></script>

```




