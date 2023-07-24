# Passo a passo para fazer um tunel do Windows para o WSL e executar os testes

## No prompt de comando WINDOWS
* `ipconfig` para salvar o valor do Endereço IPv4
* `adb -a -P 5037 nodaemon server`

* Se houver algum problema na inicialização do servidor rodar `adb kill-server`
## No terminal WSL
* `export ADB_SERVER_SOCKET=tcp:${ipv4}:5037`
* `adb devices`

## Finalmente para os testes
* `maestro --host ${ipv4} studio`
* `maestro --host ${ipv4} test ${test-name}`
* `maestro cloud app/${apk-name} .maestro/${test-name}`
