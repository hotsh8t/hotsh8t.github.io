---
title: "Errors"
categories:
  - Errors
tags:
  - content
  - css
  - edge case
  - lists
  - markup
---

#### ❌ Please append `--trace` to the `serve` command for any additional information or backtrace. 
```
                    ------------------------------------------------
      Jekyll 4.2.0   Please append `--trace` to the `serve` command 
                     for any additional information or backtrace. 
                    ------------------------------------------------
```

### ❕해결방법 : bundle exec jekyll serve --trace


### ❌ /var/lib/gems/2.5.0/gems/safe_yaml-1.0.5/lib/safe_yaml/load.rb:143:in `parse': (/home/user/HubGit/hotsh8t.github.io/_data/navigation.yml): did not find expected key while parsing a block mapping at line 2 column 1 (Psych::SyntaxError)



```
/var/lib/gems/2.5.0/gems/safe_yaml-1.0.5/lib/safe_yaml/load.rb:143:in `parse': (/경로/문제파일.yml): did not find expected key while parsing a block mapping at line 2 column 1 (Psych::SyntaxError)

```

### ❕ 해결방법 : yml 파일은 dent 를 정확하게 계산하여 입력하여야 함
