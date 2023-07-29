# GoLang-Install
Install latest version of Golang

```bash
os=`uname|tr '[:upper:]' '[:lower:]'`
go_filename=`curl -s https://go.dev/dl/?mode=json|jq '.[0].files[].filename'|grep $os|grep $arch|egrep -v "ppc"|tr -d '"'`
wget https://go.dev/dl/$go_filename
tar -C /usr/local -xzf $go_filename && rm -f $go_filename
export PATH=$PATH:/usr/local/go/bin
echo export PATH=$PATH:/usr/local/go/bin >> /root/.bashrc
```
