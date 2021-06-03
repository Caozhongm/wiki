## v2.1.1

- **新特性**
    1. 加入对 esp8266 和 makeymakey 的支持。
    2. 加入显示所有可连接设备的按钮。避免用户在使用为收录的usb转串口芯片时无法连接设备。
    3. 加入.ob工程文件关联。

- **修复BUG**
    1. 多次切换编辑目标后会严重卡顿。
    2. 配置错误的远程资源地址后点击检查更新的按钮软件会崩溃。
    3. 远程资源使用了openblockcc的地址而非配置中的设定值。
    4. 在工作区使用工具箱中嵌套结构的积木时，在更新禁用状态后，内部嵌套积木会被错误的禁用。
    5. 在打开多个窗口是会报错：地址已经使用。

## v2.1.0

- **新特性**
    1. 变更 Arduino 构架工具由 arduino-builder 为 arduino-cli.
    2. 加入外部插件和设备远程升级功能。
    3. 变更默认角色为恶魔小鸟。
    4. 加入对 arduino esp32 控制板的支持。
    5. 加入对 microbit V2 控制板的支持。
    6. 加入清除缓存按钮。
    7. 加入安装驱动按钮。
    8. 移动实时模式连接指示器到舞台区上方。
    9. 为桌面版警告弹窗加入本地化翻译。
    10. 加入上传超时报错。如果卡在上传界面几十秒后，会显示上传超时报错，使得用户可以点击关闭按钮而不是永久卡在上传界面。
    11. 加入 arduino uno ultra基础控制板以支持包含 A6，A7 引脚的定制控制板。
    12. 优化外部插件构架。
    13. 优化固件文件结构。
    14. 优化串口构架。防止在接收到大量的串口数据时导致的界面卡顿。
    15. 加入 QDP ROBOT C02 套件 (arduino esp32)。

- **修复BUG**
    1. 如果在 arduino 构建过程中拔掉 usb 线缆，会卡在上传界面。
    2. 在上传过程中拔掉 usb 线缆，gui 界面却没有显示断开设备，导致用户可以再次点击上传按钮而卡在上传界面。
    3. 在连接和断开几次设备后再次上传程序或固件会导致实时模式通讯故障。
    4. 在上传成功后如果不关闭窗口就拔掉 usb 线，会显示上传失败。

## v2.0.0

- **新特性**
    1. 加入串口终端界面。
    2. 从打包中分离第三方衍生设备代码，现在可通过修改外部配置文件控制设备选择界面中的内容了，而不需要重新打包。
    3. 优化积木在不同编程模式下的禁用逻辑。
    4. 实时模式下可以在插件选择界面中选取原本被屏蔽的实时模式插件了。
    5. 积木在没有连接有效代码生成主体时，其 define、step 等非本体的设置代码，现在不会在代码区生成了。
    6. 调整 Arduino 代码生成器生成代码的结构，使之更符合 Arduino 原生代码格式。
    7. 工程文件会保存当前的编程模式, 加载后自动切换至保存时的模式。
    8. 编程模式下积木不再能被点击执行和发光了。
    9. 实时模式通讯建立成功后不在弹窗，而通过连接图标右侧的通讯图标的暗灭来指示通讯是否成功。仅在尝试通信失败后才会弹出警告窗口并提示下载实时模式固件。
    10. 下载固件且实时通讯建立成功后，实时模式失败警告的弹窗将会自动消失。

- **修复BUG**
    1. 在加载具有多个大型插件的工程文件时，会出现工具栏区重复显示多个插件内容而有些则未被加载等错误。
    2. 在无连接设备时，下载固件的按钮没有被禁用。
    3. 缩短上传信息的显示窗口，以修复在部分设备上窗口显示不完整的问题。
    4. 修复大量有关实时模式通讯的潜在问题。
    5. 代码窗在调整窗口大小后没有重新渲染导致显示缺失一块。
    6. 切换编程模式等后角色会消失。
    7. Arduino 和 Microbit 在编程模式下没有隐藏全部的不支持积木。
    8. Microbit 的 buttonIsPressed 积木转码函数按键B时本应为 b 写成了 n。
    9. Microbit 自定义变量名称异常问题。
    10. Arduino UNO Mega2560 串口0转译代码不正确。
    11. 变量设置增加的积木块的数字解析错误。
    12. 取消1.05倍界面缩放设置，直接改大字体以修复工具栏菜单字体模糊的问题。

## v1.2.2beta

- **新特性**
    1. 添加隐藏代码区按键。
    2. 变更上传按键的外观设计。
    3. 更改一些控制板的描述。
    4. 增加1.05倍界面缩放用以修复部分设备上字体模糊的问题。
    5. 变更工程文件扩展名由 .sb3 为 .ob。

- **修复BUG**
    1. Microbit 代码生成器错误。
    2. Arduino 设置数字输出的引脚菜单中没有模拟引脚选项。

## v1.2.1beta

- **新特性**
    1. 添加隐藏代码区按钮。
    2. 变更上传按钮外观。
    3. 变更一些控制板的描述，以适应中国广告法。
    4. 添加1.05倍缩放以修复字体模糊问题。

- **修复BUG**
    1. Microbit 代码生成不工作。
    2. Arduino 数字输出积木的引脚菜单选项内没有模拟引脚。
    3. 第三方套件由基础控制板继承的积木块代码转译功能错误。

## v1.2.0beta

- **新特性**
    1. 现在大多数弹窗提示将会在5秒后自动消失。
    2. 完成 Microbit 的全部功能实现。
    3. 加入舵机插件作为 Mcrobit 插件的样例。
    4. 在安装新版本的 OpenBlock 软件后，旧版本留存下缓存将被自动清除。

- **新设备/套件**
    1. Arduino Mini
    2. 齐护机器人套件

- **修复BUG**
    1. 错误的CP2102硬件ID。

    2. Microbit翻译错误。
    3. 加载工程后无法扫描到设备。
    4. 选择新的设备后旧设备加载的插件仍然存在。

## v1.1.0beta

- **新特性**
    1. 在鼠标移入工具区后因为过长而隐藏部分显示的积木块会被全部显示。

    2. 在选择设备后会自动加载设定的扩展。

- **新设备/套件**
    1. Microbit

    2. Iron robot kit