# AWS_EMR
```
git clone https://github.com/thejungwon/AWS_EMR
cd AWS_EMR

curl -L -o actors.list https://www.dropbox.com/s/vofyl0uryectfyt/actors.list\?dl\=1
hadoop fs -mkdir /test
hadoop fs -put actors.list /test/actors.list

virtualenv -p python3 venv
. venv/bin/activate
pip install mrjob
cp .mrjob.conf ~/.mrjob.conf
python mr_word_freq_count.py -r hdfs:///test/actors.list --output-dir hdfs:///test/output

```
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
