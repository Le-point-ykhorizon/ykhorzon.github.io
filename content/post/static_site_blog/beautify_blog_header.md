+++
author = "ykhorizon"
date = "2018-12-10T18:03:28+08:00"
title = "Beautify blog header section - Quick refresh CSS, Bootstrap and Design 1"
categories = []
tags = []
type = "post"
draft = true
+++

## Before and After

<img src="/content_img/web_frontend_css/beautify_blog_header/before.png">

## Re-design 
### Banner Responsive background image

1. Size does matter 
    - Check the general header and banner size could be width and height of header or banner could be very diverse [[1]](https://www.freewebheaders.com/website-header-sizes/)[[2]](https://support.sharefaith.com/support/solutions/articles/1000140425-what-sizes-work-best-for-images-and-banners-). The widht could be ``1920, 1600, 1440, 1366, 1280, 1024 px`` and the ``height depened on your layout design`` .



2. Banner texture and picture selcetion

    - To make the word on banner readable 
        - Choese a simple color distribution picture (all light, dark, simuliar color)


### Title on banner (by hugo) 

### Navigation bar (navbar)

1.color, background-color and brand font

- [css-to-make-bootstrap-navbar-transparent](https://stackoverflow.com/questions/16392952/css-to-make-bootstrap-navbar-transparent)
- [transparent navbar demo code](https://www.codeply.com/go/QAXbNGbWPA/bootstrap-4-navbar-transparent)

2.buttons(related information architecture) and function



Implementations

<!-- ```css
.header-image-block {
  max-width: 100%;
  height: 600px;

  background-image: url("/img/cover1_small.jpg");
  background-repeat: no-repeat;
  background-size: cover;

  margin-bottom: 5%;
}
```

``` html 
    <div class="header-image-block">
        <nav class="navbar navbar-expand-md navbar-dark bg-dark">
            <a class="navbar-brand" href="{{ .Site.BaseURL | relLangURL }}">
                {{ partial "brand" . }}
            </a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false"
                aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse justify-content-between" id="navbarNav">
                <ul class="navbar-nav">
                    {{ $url := .URL | relLangURL }}
                    {{ range .Site.Menus.main }}
                    <li class="nav-item {{ if eq $url (.URL | relLangURL) }}active{{end}}">
                        {{ if eq (hasPrefix .URL "mailto:") true }}
                            <a class="nav-link" href="{{ .URL }}">{{ .Name }}</a>
                        {{ else }}
                            <a class="nav-link" href="{{ .URL | relLangURL }}">{{ .Name }}</a>
                        {{ end }}
                    </li>
                    {{ end }}
                </ul>
                {{ if gt (len .Site.Home.AllTranslations) 1 }}
                <ul class="navbar-nav">
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                            {{ i18n "language" }}
                        </a>
                        <div class="dropdown-menu dropdown-menu-right" aria-labelledby="navbarDropdown">
                            {{ range .Site.Home.AllTranslations }}
                                <a class="dropdown-item" href="{{ .Permalink }}">{{ .Language.LanguageName }}</a>
                            {{ end }}
                        </div>
                    </li>
                </ul>
                {{ end }}
            </div>
        </nav>
        <div class="container">
            <div class="row">
            </div>
        </div>
    </div>
```-->
## References

- [[1] Recommended Website Header Image Size for Your Site](https://www.freewebheaders.com/website-header-sizes/)
- [[2] What sizes work best for images and banners?](https://support.sharefaith.com/support/solutions/articles/1000140425-what-sizes-work-best-for-images-and-banners-)
- [Desired layout, blog.kdchang.cc](https://blog.kdchang.cc/2017/08/15/learning-programming-and-coding-with-python-list-tuple-dict-set/)
- [bootstrap](https://getbootstrap.com/docs/4.1/getting-started/introduction/)
- [w3schools](https://www.w3schools.com/css/default.asp)
- [Responsive Web Design - Images,w3schools](https://www.w3schools.com/css/css_rwd_images.asp)