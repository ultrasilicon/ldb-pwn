# LDB PWN



## Behaviour Bypass:

| Target            | Proc Name                                 | Proc Loc  | Line      | Pwn                |
| ----------------- | ----------------------------------------- | --------- | --------- | ------------------ |
| code sign check   | __Z18checkCodeSignaturev                  | 10006c310 | 10006c34c | `je loc_10006c413` |
| clear paste board | __Z15clearPasteboardv                     | 100069960 | 100069960 | `ret`              |
| kill dock         | __Z10freezeDockv                          | 10006c210 | 10006c210 | `ret`              |
| Kill other apps   | -[LDBAppController checkRunningProcesses] | 100112340 | 100112340 | `ret`              |
|                   |                                           |           |           |                    |
|                   |                                           |           |           |                    |
|                   |                                           |           |           |                    |
|                   |                                           |           |           |                    |
|                   |                                           |           |           |                    |



## UI Bypass:

| Target                 | Proc Name                                               | Proc Loc  | Line      | Pwn                      |
| ---------------------- | ------------------------------------------------------- | --------- | --------- | ------------------------ |
| minimize button        | -[LDBAppDelegate applicationDidFinishCefInitialization] | 1000abe00 | 1000abf1a | `mov edx, 0x0`           |
| maximize button        | -[LDBAppDelegate applicationDidFinishCefInitialization] | 1000abe00 | 1000abf64 | `mov edx, 0x0`           |
| fullscreen button      | -[LDBAppDelegate applicationDidFinishCefInitialization] | 1000abe00 | 1000abfae | `mov edx, 0x0`           |
| desktop switch?        | imp\_\_\_stubs\_\_SetSystemUIMode                       | 100197004 | 100197004 | `ret`                    |
| shielding window?      | -[LDBAppController createShieldingWindows]              | 10010f900 | 10010f900 | `ret`                    |
| dock                   | __Z10freezeDockv                                        | 10006c210 | 10006c210 | `ret`                    |
| keep on current screen | -[LDBAppDelegate applicationDidFinishCefInitialization] | 1000abe00 | 1000abecc | `mov edx, 0x0`           |
| Notification Center    | -[LDBAppController saveNotifyCenterAndDisable]          | 100110db0 | 100110db0 | `ret`                    |
| hide other app         | -[LDBAppDelegate applicationDidFinishCefInitialization] | 1000abe00 | 1000ac07f | `nop` block              |
| set window movable     | -[LDBAppDelegate applicationDidFinishLaunching:]        | 1000ab810 | 1000abb69 | `and edx, edx`           |
| enable new tab button  | -[LDBAppDelegate applicationDidFinishLaunching:]        | 1000ab810 | 1000abb8e | `mov edx, 0x0`           |
| keep focus             | -[LDBAppDelegate applicationDidResignActive:]           | 1000ace20 | 1000acff8 | `mov edx, 0x0`           |
| put other app behind   | -[LDBAppDelegate applicationDidResignActive:]           | 1000ace20 | 1000acfec | `xchg ax,ax`             |
| enable tab dragging    | -[LDBTabBrowserWindowController tabDraggingAllowed]     | 100094f60 | 100094f64 | `and eax, eax`           |
| enable tab tearing     | -[LDBTabBrowserWindowController tabTearingAllowed]      | 100094f70 | 100094f74 | `and eax, eax`           |
| hiding tab             | -[LDBTabBrowser hideTabAtIndex:]                        | 100091710 | 100091710 | `ret`                    |
| lock window move       | -[LDBTabBrowserWindowController windowDidMove:]         | 100095b50 | 100095b50 | `ret`                    |
| lock window move       | -[LDBTabBrowserWindowController windowWillMove:]        | 100095ab0 | 100095ab0 | `ret`                    |
| set manu bar visible 1 | -[LDBAppController awakeFromNib]                        | 1000fe550 | 1000fe5ba | `xchg ax,ax`             |
| set manu bar visible 2 | -[LDBAppController killProcessesTimerCallback:]         | 1000fe8a0 | 1000fe8d9 | `nop word ptr [eax+eax]` |
|                        |                                                         |           |           |                          |
|                        |                                                         |           |           |                          |
|                        |                                                         |           |           |                          |
|                        |                                                         |           |           |                          |
|                        |                                                         |           |           |                          |
|                        |                                                         |           |           |                          |
|                        |                                                         |           |           |                          |
​	

