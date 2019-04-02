# AWS_EMR
```
vi ~/.mrjob.conf
```
```
{
  "runners": {
    "hadoop": {
      "setup": [
        "set -e"
      ],
      "sh_bin": "/bin/bash -x"
    }
  }
}
```
