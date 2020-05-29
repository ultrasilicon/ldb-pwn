# LDB PWN



## Behaviour Bypass:

| Target            | Proc Name                | Proc Loc  | Line      | Pwn                |
| ----------------- | ------------------------ | --------- | --------- | ------------------ |
| code sign check   | __Z18checkCodeSignaturev | 10006c310 | 10006c34c | `je loc_10006c413` |
| clear paste board | __Z15clearPasteboardv    | 100069960 | 100069960 | `ret`              |
| Kill dock         | __Z10freezeDockv         | 10006c210 | 10006c210 | `ret`              |
|                   |                          |           |           |                    |
|                   |                          |           |           |                    |
|                   |                          |           |           |                    |
|                   |                          |           |           |                    |
|                   |                          |           |           |                    |
|                   |                          |           |           |                    |



## UI Bypass:

| Target            | Proc Name                                               | Proc Loc  | Line      | Pwn               |
| ----------------- | ------------------------------------------------------- | --------- | --------- | ----------------- |
| minimize button   | -[LDBAppDelegate applicationDidFinishCefInitialization] | 1000abe00 | 1000abf1a | `mov    edx, 0x0` |
| maximize button   | -[LDBAppDelegate applicationDidFinishCefInitialization] | 1000abe00 | 1000abf64 | `mov    edx, 0x0` |
| fullscreen button | -[LDBAppDelegate applicationDidFinishCefInitialization] | 1000abe00 | 1000abfae | `mov    edx, 0x0` |
| desktop switch?   | imp\_\_\_stubs\_\_SetSystemUIMode                       | 100197004 | 100197004 | `ret`             |
| shielding window? | -[LDBAppController createShieldingWindows]              | 10010f900 | 10010f900 | `ret`             |
| dock              | __Z10freezeDockv                                        | 10006c210 | 10006c210 | `ret`             |
|                   |                                                         |           |           |                   |
|                   |                                                         |           |           |                   |
|                   |                                                         |           |           |                   |

​	
