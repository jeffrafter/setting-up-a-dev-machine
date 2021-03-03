```
# From @mikekavouras
function gh-server
  argparse s/ssl d/debug -- $argv
  if set -q _flag_ssl
    env GH_SSL=1 bin/server --debug
  else
    bin/server --debug
  end
end

function gh-test
  argparse a/all-features -- $argv
  if set -q _flag_all_features
    env TEST_ALL_FEATURES=1 bin/rails test $argv[1]
  else
    bin/rails test $argv[1]
  end
end
```

Usage:

```
gh-test --all-features <FILENAME>
``` 

and 

```
gh-server --ssl
```