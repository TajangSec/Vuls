`dst-admin\src\main\java\com\tugos\dst\admin\controller\HomeController.java` presence function `cavesConsole`.

This function takes a "command" parameter and passes it to `shellService.masterConsole`.

![](C:\Users\Tajang\Desktop\dst-admin_v1.5.0_rce_1.png)

The masterConsole parameter is processed and passed into the `ShellUtil.execShellBin`

![Clip_2024-01-30_15-54-49](C:\Program Files\PixPin\Temp\Clip_2024-01-30_15-54-49.png)

`execShellBin` will use `/bin/sh -c` to execute the argument

![Clip_2024-01-30_15-57-36](C:\Program Files\PixPin\Temp\Clip_2024-01-30_15-57-36.png) 

To exploit this vulnerability, you need to have administrator privileges, and the default password for administrators is admin / 123456.

Log in to the backend and execute the command as shown below

![Clip_2024-01-30_16-02-18](C:\Program Files\PixPin\Temp\Clip_2024-01-30_16-02-18.png)

DNSlog receives the resolution log

![Clip_2024-01-30_16-02-42](C:\Program Files\PixPin\Temp\Clip_2024-01-30_16-02-42.png)

shodan：`http.title:"饥荒管理后台"`