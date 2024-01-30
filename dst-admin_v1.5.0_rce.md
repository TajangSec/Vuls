`dst-admin\src\main\java\com\tugos\dst\admin\controller\HomeController.java` presence function `cavesConsole`.

This function takes a "command" parameter and passes it to `shellService.masterConsole`.

![image](https://github.com/TajangSec/Vuls/assets/63721558/bc82ff21-a36e-48e4-a663-096cc08c57c4)


The masterConsole parameter is processed and passed into the `ShellUtil.execShellBin`
![image](https://github.com/TajangSec/Vuls/assets/63721558/eb0ac89b-840e-4bb2-a072-fb385bc58277)


`execShellBin` will use `/bin/sh -c` to execute the argument

![image](https://github.com/TajangSec/Vuls/assets/63721558/56085aeb-4f8f-46c3-ac8d-6ac99486697e)


To exploit this vulnerability, you need to have administrator privileges, and the default password for administrators is admin / 123456.

Log in to the backend and execute the command as shown below

![image](https://github.com/TajangSec/Vuls/assets/63721558/f474e7c9-f68f-467a-a8c9-add81564162e)


DNSlog receives the resolution log

![image](https://github.com/TajangSec/Vuls/assets/63721558/8c96540f-ff29-4f9e-86f3-8aa640508314)


shodan：`http.title:"饥荒管理后台"`
