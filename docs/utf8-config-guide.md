# PowerShell UTF-8 配置指南

## 问题背景

在使用 PowerShell 7 (pwsh) 时，经常会遇到中文和特殊字符显示乱码的问题。这是因为 Windows 系统默认的编码设置不总是支持 UTF-8。

## 解决方案

### 方法一：修改 PowerShell Profile（推荐）

在 PowerShell Profile 文件中添加以下配置：

```powershell
# PowerShell 7 UTF-8 配置
# 设置UTF-8编码以支持中文和特殊字符

# 设置控制台编码为UTF-8
[Console]::OutputEncoding = [System.Text.Encoding]::UTF8
[Console]::InputEncoding = [System.Text.Encoding]::UTF8

# 设置PowerShell内部编码为UTF-8
$OutputEncoding = [System.Text.Encoding]::UTF8

# 设置代码页为UTF-8 (65001)
try {
    chcp 65001 | Out-Null
} catch {
    # 忽略可能的错误
}

# 设置环境变量以支持UTF-8
$env:LANG = "en_US.UTF-8"
$env:LC_ALL = "en_US.UTF-8"
$env:PYTHONIOENCODING = "utf-8"
```

### 方法二：系统级设置（Windows 10/11）

1. 打开 **设置** → **时间和语言** → **语言和区域**
2. 点击 **管理语言设置**
3. 在 **区域** 对话框中：
   - 在 **格式** 选项卡选择合适的格式
   - 在 **管理** 选项卡，点击 **更改系统区域设置**
   - 勾选 **Beta: 使用 Unicode UTF-8 提供全球语言支持**
4. 重启系统

### 方法三：临时设置

每次打开 PowerShell 时运行：

```powershell
chcp 65001
$env:PYTHONIOENCODING = "utf-8"
```

## 配置说明

### 各项配置的作用

1. **`[Console]::OutputEncoding`**
   - 设置 PowerShell 控制台输出的编码
   - 影响 `Write-Host` 和命令输出

2. **`[Console]::InputEncoding`**
   - 设置 PowerShell 控制台输入的编码
   - 影响键盘输入和管道输入

3. **`$OutputEncoding`**
   - 设置 PowerShell 向外部程序发送数据的编码
   - 影响 `Write-Output` 和管道操作

4. **`chcp 65001`**
   - `chcp` 是 Change Code Page 的缩写
   - 65001 是 UTF-8 的代码页编号
   - 设置命令提示符的编码页

5. **环境变量**
   - `$env:LANG` 和 `$env:LC_ALL`：Unix 风格的语言设置
   - `$env:PYTHONIOENCODING`：Python 的 I/O 编码设置

## PowerShell Profile 文件位置

### Windows PowerShell (powershell.exe)
```
C:\Users\[用户名]\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
```

### PowerShell Core (pwsh)
```
C:\Users\[用户名]\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
```

### 所有用户的 Profile
- 系统级：`$PSHOME\Profile.ps1`
- 所有用户：`C:\Program Files\PowerShell\7\Profile.ps1`

## 常见问题

### Q: 为什么中文字符还是显示乱码？
A: 可能的原因：
1. 字体不支持 Unicode（建议使用 Cascadia Code、Consolas 或其他支持 Unicode 的字体）
2. 终端程序不支持 UTF-8（Windows Terminal 推荐使用）
3. 需要重启 PowerShell 或系统

### Q: `chcp 65001` 失败怎么办？
A: 在某些旧版本 Windows 中，可能需要管理员权限或使用其他方法。

### Q: Python 脚本输出中文乱码？
A: 设置 `PYTHONIOENCODING=utf-8` 环境变量可以解决。

## 验证配置

运行以下命令验证 UTF-8 配置是否生效：

```powershell
# 查看控制台编码
[Console]::OutputEncoding

# 查看代码页
chcp

# 测试中文输出
Write-Host "测试中文：你好世界！🌟"

# 测试特殊字符
Write-Host "特殊字符：αβγ ΔΣπ ✓✗"
```

## 最佳实践

1. **优先使用 PowerShell Profile**：设置一次，永久生效
2. **使用 Windows Terminal**：对 Unicode 支持更好
3. **选择合适的字体**：确保字体支持 Unicode
4. **保持一致性**：在不同设备上使用相同的配置

## 相关资源

- [About Character Encoding - Microsoft Docs](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_character_encoding)
- [UTF-8 Support - Windows Docs](https://docs.microsoft.com/windows/uwp/design/globalizing/use-utf8-code-page)
- [Windows Terminal - GitHub](https://github.com/microsoft/terminal)