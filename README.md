# CLI Daily Greeting / CLI 毎日あいさつ / 每日终端问候语

[中文](#中文) | [English](#english) | [日本語](#日本語)

---

## 中文

为PowerShell终端添加随机欢迎语，每次打开时都能获得不同的智慧和启发。

### 功能特色

- 🎲 **随机显示**：从数百条精选语句中随机选择一条
- 📚 **内容丰富**：包含编程智慧、人生哲理、《论语》、《孙子兵法》等国学经典
- 🎨 **彩色输出**：绿色文字清晰醒目
- ⚡ **轻量快速**：不影响启动速度
- 🛠️ **易于定制**：可以轻松添加或修改语句

### 安装方法

#### 方法一：直接使用（推荐）

1. 下载 `Microsoft.PowerShell_profile.ps1` 文件
2. 将其复制到您的PowerShell配置目录：
   - Windows PowerShell: `C:\Users\[用户名]\Documents\WindowsPowerShell\`
   - PowerShell Core: `C:\Users\[用户名]\Documents\PowerShell\`
3. 重新打开PowerShell即可看到效果

#### 方法二：手动添加

如果您已有PowerShell Profile文件，只需将代码添加到文件末尾。

### 自定义

您可以轻松添加自己的语句或创建不同主题。

### UTF-8 支持

配置文件包含完整的 UTF-8 编码设置，确保中文和特殊字符正确显示：
- 控制台输入输出编码
- PowerShell 内部编码
- 代码页设置 (65001)
- 环境变量配置

详细说明请参考：[UTF-8 配置指南](docs/utf8-config-guide.md)

### 示例效果

```
从一个胜利走向另一个胜利！
PS C:\Users\DELL>
```

### 文件结构

```
cli_greeting/
├── Microsoft.PowerShell_profile.ps1    # 主配置文件
├── quotes/                              # 引用语料库
│   ├── analects.md                      # 《论语》名句
│   └── art-of-war.md                    # 《孙子兵法》名句
├── docs/                                # 文档
│   └── utf8-config-guide.md             # UTF-8配置指南
└── README.md                            # 项目说明
```

---

## English

Add random greetings to your PowerShell terminal. Get a different dose of wisdom and inspiration every time you open it.

### Features

- 🎲 **Random Display**: Selects randomly from hundreds of curated quotes
- 📚 **Rich Content**: Programming wisdom, life philosophy, Chinese classics including The Analects and The Art of War
- 🎨 **Colorful Output**: Clear and prominent green text
- ⚡ **Lightweight**: No impact on startup speed
- 🛠️ **Customizable**: Easy to add or modify quotes

### Installation

#### Method 1: Direct Use (Recommended)

1. Download `Microsoft.PowerShell_profile.ps1`
2. Copy to your PowerShell config directory:
   - Windows PowerShell: `C:\Users\[Username]\Documents\WindowsPowerShell\`
   - PowerShell Core: `C:\Users\[Username]\Documents\PowerShell\`
3. Reopen PowerShell to see the effect

#### Method 2: Manual Addition

Add the code to the end of your existing PowerShell Profile file.

### Customization

Easily add your own quotes or create different themes.

### UTF-8 Support

The configuration file includes complete UTF-8 encoding settings to ensure Chinese and special characters display correctly:
- Console input/output encoding
- PowerShell internal encoding
- Code page settings (65001)
- Environment variable configuration

For details, see: [UTF-8 Configuration Guide](docs/utf8-config-guide.md)

### Example Effect

```
Code changes the world, today is full of possibilities!
PS C:\Users\DELL>
```

### File Structure

```
cli_greeting/
├── Microsoft.PowerShell_profile.ps1    # Main configuration file
├── quotes/                              # Quote library
│   ├── analects.md                      # The Analects quotes
│   └── art-of-war.md                    # The Art of War quotes
├── docs/                                # Documentation
│   └── utf8-config-guide.md             # UTF-8 configuration guide
└── README.md                            # Project documentation
```

---

## 日本語

PowerShellターミナルにランダムな挨拶を追加します。開くたびに異なる知恵とインスピレーションを得られます。

### 特徴

- 🎲 **ランダム表示**: 数百の厳選された引用からランダムに選択
- 📚 **豊富なコンテンツ**: プログラミングの知恵、人生哲学、論語、孫子の兵法などの中国古典
- 🎨 **カラフル出力**: 目立つ緑色のテキスト
- ⚡ **軽量**: 起動速度に影響なし
- 🛠️ **カスタマイズ可能**: 引用の追加や変更が簡単

### インストール

#### 方法1: 直接使用（推奨）

1. `Microsoft.PowerShell_profile.ps1` をダウンロード
2. PowerShell設定ディレクトリにコピー:
   - Windows PowerShell: `C:\Users\[ユーザー名]\Documents\WindowsPowerShell\`
   - PowerShell Core: `C:\Users\[ユーザー名]\Documents\PowerShell\`
3. PowerShellを再開して効果を確認

#### 方法2: 手動追加

既存のPowerShellプロファイルファイルの末尾にコードを追加します。

### カスタマイズ

独自の引用を追加したり、異なるテーマを作成したりできます。

### UTF-8 サポート

設定ファイルには、中国語や特殊文字が正しく表示されるように完全なUTF-8エンコーディング設定が含まれています：
- コンソール入出力エンコーディング
- PowerShell内部エンコーディング
- コードページ設定（65001）
- 環境変数設定

詳細はこちら：[UTF-8設定ガイド](docs/utf8-config-guide.md)

### 例

```
ある勝利から別の勝利へ！
PS C:\Users\DELL>
```

### ファイル構成

```
cli_greeting/
├── Microsoft.PowerShell_profile.ps1    # メイン設定ファイル
├── quotes/                              # 引用ライブラリ
│   ├── analects.md                      # 論語の引用
│   └── art-of-war.md                    # 孫子の兵法の引用
├── docs/                                # ドキュメント
│   └── utf8-config-guide.md             # UTF-8設定ガイド
└── README.md                            # プロジェクトドキュメント
```

---

## Contributing / 贡献 / 貢献

欢迎提交Pull Request添加更多有意义的语句！
Welcome to submit Pull Requests to add more meaningful quotes!
意味のある引用を追加するために、プルリクエストを歓迎します！

## License / 许可证 / ライセンス

MIT License - 自由に使用および変更してください
MIT License - Use and modify freely
MITライセンス - 自由に使用・変更してください