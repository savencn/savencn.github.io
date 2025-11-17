# 开启/取消按 Ctrl+Alt+Delete 登录系统的解决方法（Windows 11+）

[toc]

## 了解 Ctrl+Alt+Delete 的用途

**Ctrl+Alt+Delete** 组合键在 Windows 系统中用于打开"Windows 安全"屏幕，提供锁定计算机、注销用户、更改密码、启动任务管理器等功能。在 Windows 11 及以后版本中，它作为一种*安全机制*，确保只有合法用户才能访问系统。但有时用户可能希望取消或开启此功能以简化登录过程或增强安全性。

---

## 方法一：通过用户账户设置（推荐）

!!! abstract **操作步骤：**

    1. 按下 `Win + R`，输入 `netplwiz`
    2. 切换到"高级"选项卡
    3. **取消**：取消勾选"要求用户按 Ctrl+Alt+Delete"
       **开启**：勾选"要求用户按 Ctrl+Alt+Delete"
    4. 点击"应用"，重启电脑



## 方法二：Windows 安全设置（Windows 11 特有）

!!! abstract **操作步骤：**

    1. 打开"设置" → "账户" → "登录选项"
    2. 找到"要求 Windows Hello 登录"或"需要 Windows Hello 登录"
    3. **取消**：关闭此选项
       **开启**：开启此选项（如果支持 Windows Hello）
    4. 或者查找"登录时需要按 Ctrl+Alt+Delete"相关设置



## 方法三：组策略编辑器（适用于专业版/企业版/教育版）

!!! abstract **操作步骤：**

    1. 按下 `Win + R`，输入 `gpedit.msc`
    2. 导航到：`计算机配置` → `Windows 设置` → `安全设置` → `本地策略` → `安全选项`
    3. 找到"交互式登录：不需要按 Ctrl+Alt+Delete"策略
    4. **取消**：设置为"已启用"
       **开启**：设置为"已禁用"或"未配置"



## 方法四：注册表编辑器（适用于家庭版）

!!! warning **警告：修改注册表有风险，请谨慎操作！建议先备份注册表。**
!!! abstract    **操作步骤：**

    1. 按下 `Win + R`，输入 `regedit`
    2. 导航到：`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\policies\System`
    3. **取消**：新建 DWORD 值 `DisableCAD`，设置为 `1`
       **开启**：将 `DisableCAD` 值设置为 `0` 或删除该值
    4. 重启电脑



## Windows 11 注意事项

!!! attention **注意事项:**
    1. **⚠️ 重要提醒** - **Windows 11** 默认推荐使用 Windows Hello（面部识别、指纹、PIN 码）等更安全的登录方式 - 取消 Ctrl+Alt+Delete _可能会降低系统安全性_ - 建议在安全的家庭或办公环境中使用此设置 - 企业环境中可能需要遵循公司的安全策略
    2. **📝 提示：** 以上方法按推荐程度排序，建议优先尝试方法一和方法二。
    3. **💡 小贴士：** 如果某个方法不适用或无效，请尝试下一个方法。
    4. **🔄 重启生效：** 修改设置后，通常需要重启电脑以使更改生效。
