# alp

https://github.com/tkuchiki/alp

## インストール

```sh
wget https://github.com/tkuchiki/alp/releases/download/v1.0.21/alp_linux_amd64.tar.gz
tar -zxvf alp_linux_amd64.tar.gz
sudo install alp /usr/local/bin/alp
rm alp alp_linux_amd64.tar.gz
alp --version
```

## alpのプロファイル手順

1. アクセスログのリセット

```sh
sudo truncate -s 0 ${ACCESS_LOG} && sudo chown syslog:adm ${ACCESS_LOG}
```

2. ベンチマーク実行
3. alpによる集計

```sh
sudo cat ${ACCESS_LOG} | '${ALP_BIN}' json --sort avg --output count,method,uri,min,max,sum,avg,p99"
```
