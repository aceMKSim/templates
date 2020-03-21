# `tufte.zip` 사용법

texlive와 아래의 패키지들이 설치되어 있는 환경에서...

```r
install.packages("rmarkdown")
install.packages("rticles")
install.packages("tufte")
```

1. 다운받아 압축을 풀고
2. `tufte_template.Rmd`를 RStudio로 Open해서
3. Knit하면 tufte handout 문서가 생성됨
4. 문서 포맷의 종류는 아래와 같음
    + html 
    + handout (pdf)
    + book (pdf)

# 기타 pdf 문서의 한글사용 활성화

+ YAML Header의 `output` 블락에 아래와 같이 `includes: in_header:`에 해당하는 부분을 조정해주어야 함.
+ `bookdown`등의 패키지에도 비슷한 원리로 한글 사용을 활성화 할 수 있음.

```YAML
output:
  tufte::tufte_handout:
    citation_package: natbib
    latex_engine: xelatex
    includes:    
      in_header: rmd-pdf-support/latex-topmatter.tex 
  tufte::tufte_book:
    citation_package: natbib
    latex_engine: xelatex
    includes:
      in_header: rmd-pdf-support/latex-topmatter.tex
  tufte::tufte_html: default
  ```
