# CLI Daily Greeting - PowerShell随机欢迎语

为PowerShell终端添加随机欢迎语，每次打开时都能获得不同的智慧和启发。

## 功能特色

- 🎲 **随机显示**：从数百条精选语句中随机选择一条
- 📚 **内容丰富**：包含编程智慧、人生哲理、国学经典
- 🎨 **彩色输出**：绿色文字清晰醒目
- ⚡ **轻量快速**：不影响启动速度
- 🛠️ **易于定制**：可以轻松添加或修改语句

## 安装方法

### 方法一：直接使用（推荐）

1. 下载 `Microsoft.PowerShell_profile.ps1` 文件
2. 将其复制到您的PowerShell配置目录：
   - Windows PowerShell: `C:\Users\[用户名]\Documents\WindowsPowerShell\`
   - PowerShell Core: `C:\Users\[用户名]\Documents\PowerShell\`
3. 重新打开PowerShell即可看到效果

### 方法二：手动添加

如果您已有PowerShell Profile文件，只需将以下代码添加到文件末尾：

```powershell
# 随机欢迎语
$welcomeMessages = @(
    "从一个胜利走向另一个胜利！",
    "代码改变世界，今天又是充满可能性的一天！",
    "保持好奇，持续学习！",
    # ... 更多语句见 quotes.md
)

$randomMessage = Get-Random -InputObject $welcomeMessages
Write-Host $randomMessage -ForegroundColor Green
```

## 文件说明

- `Microsoft.PowerShell_profile.ps1` - 主配置文件
- `quotes/` - 所有欢迎语句集合
  - `programming.md` - 编程相关语句
  - `analects.md` - 《论语》经典名句
  - `wisdom.md` - 智慧哲理语句
- `themes/` - 不同主题的配置文件（可选）

## 自定义语句

您可以：
1. 在 `$welcomeMessages` 数组中直接添加新语句
2. 编辑 `quotes/` 目录下的文件
3. 创建自己的主题配置文件

## 示例效果

```
PS C:\Users\Username> 从一个胜利走向另一个胜利！
PS C:\Users\Username>
```

每次打开PowerShell都会显示不同的绿色欢迎语句。

## 贡献

欢迎提交Pull Request添加更多有意义的语句！

## License

MIT License - 随意使用和修改