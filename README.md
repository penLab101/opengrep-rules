# opengrep-rules

```sh
semgrep-rules-manager --dir ./rules download
# https://github.com/iosifache/semgrep-rules-manager/blob/main/action.yaml
# git add ... # do backup first
find rules/ \( -type f -name '.*.ymal' \) -exec rm -rf {} +
find rules/ \( -type d -name '.github' \) -exec rm -rf {} +
```

```sh
# [semgrep-rules] # https://github.com/semgrep/semgrep-rules
# [autogrep filtered-rules] # https://github.com/lambdasec/autogrep.git
```
