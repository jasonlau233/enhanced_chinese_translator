# Enhanced Chinese Translator

[![PyPI version](https://badge.fury.io/py/enhanced-chinese-translator.svg)](https://badge.fury.io/py/enhanced-chinese-translator)
[![Python versions](https://img.shields.io/pypi/pyversions/enhanced-chinese-translator.svg)](https://pypi.org/project/enhanced-chinese-translator/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

🚀 **专业的代码中文转英文翻译工具** - 专门为开发者设计的高性能翻译工具，支持项目代码内的注释、print语句、字符串等中文内容的批量翻译，让您的代码国际化更简单！

## 🎯 主要用途

✨ **代码注释翻译**: 一键翻译 Python、JavaScript、Dart、Java 等各种编程语言的中文注释  
📝 **字符串内容翻译**: 智能识别并翻译代码中的中文字符串和print语句  
🔄 **批量处理**: 支持整个项目目录的批量翻译，大幅提升开发效率  
🎨 **格式保持**: 完美保持代码原有格式、缩进和结构不变  
⚡ **多线程处理**: 高性能并发翻译，快速处理大型项目  

## 💡 适用场景

- 🌍 **代码国际化**: 将中文代码项目翻译为英文，便于国际协作
- 📚 **开源项目**: 让中文开源项目更容易被国际开发者理解
- 🏢 **企业项目**: 公司代码库的多语言支持和规范化
- 📖 **文档翻译**: 代码文档和注释的专业翻译

## ✨ 核心特性

🚀 **智能识别**: 自动识别代码中的中文注释、字符串、print语句等内容  
🎯 **精准翻译**: 基于编程上下文的智能翻译，保持技术术语准确性  
💾 **智能缓存**: 线程安全的翻译缓存，避免重复API调用，节省成本  
⚡ **批量处理**: 多文件并发处理，支持自定义文件类型过滤  
🛡️ **安全备份**: 翻译前自动创建备份，确保原始代码安全  
📊 **性能监控**: 详细的处理统计和进度跟踪  

## 🔧 支持的编程语言

- **前端开发**: JavaScript (.js), TypeScript (.ts), Vue (.vue), React (.jsx, .tsx)
- **移动开发**: Dart (.dart), Swift (.swift), Kotlin (.kt)  
- **后端开发**: Python (.py), Java (.java), C++ (.cpp), C# (.cs)
- **其他语言**: PHP (.php), Go (.go), Rust (.rs), Ruby (.rb)
- **配置文件**: JSON (.json), YAML (.yaml), XML (.xml)
- **文档文件**: Markdown (.md), 文本文件 (.txt)

## Features

✨ **Multi-threaded Processing**: Concurrent translation with configurable worker threads  
🚀 **Batch Translation**: Process multiple texts simultaneously for improved efficiency  
💾 **Smart Caching**: Thread-safe translation cache to avoid duplicate API calls  
🎯 **Context-Aware**: Handles strings, comments, and code contexts intelligently  
⚡ **Rate Limiting**: Built-in API rate limiting to prevent service throttling  
📁 **Directory Processing**: Batch process entire directories with file filtering  
🔄 **Multiple Services**: Support for Google Translate, Baidu, and other services  
📊 **Performance Stats**: Detailed statistics and progress tracking  
🛡️ **Backup Support**: Automatic backup creation before translation  
🎨 **Smart Text Processing**: Preserves programming terms and handles mixed content

## Installation

### From PyPI (Recommended)

```bash
pip install enhanced-chinese-translator
```

### From Source

```bash
git clone https://github.com/enhanced-translator/enhanced-chinese-translator.git
cd enhanced-chinese-translator
pip install -e .
```

## Quick Start

### Command Line Usage

```bash
# Translate a single file
enhanced-chinese-translator my_file.py

# Use short command alias
ect my_file.py

# Translate entire directory
ect /path/to/project --patterns "*.py" "*.dart" "*.js"

# Advanced usage with custom settings
ect /path/to/project \
    --workers 10 \
    --batch-size 20 \
    --rate-limit 0.02 \
    --output /path/to/translated \
    --no-backup
```

### Python API Usage

```python
from enhanced_chinese_translator import EnhancedChineseTranslator

# Initialize translator
translator = EnhancedChineseTranslator(
    translation_service='google',
    max_workers=5,
    batch_size=10,
    rate_limit=0.05
)

# Translate a single file
success = translator.translate_file('my_file.py')

# Translate multiple files in directory
count = translator.translate_directory(
    '/path/to/project',
    file_patterns=['*.py', '*.dart'],
    backup=True
)

# Batch translate texts
texts = ["你好世界", "这是一个测试", "中文翻译"]
translations = translator.translate_texts_batch(texts)

# Print performance statistics
translator.print_performance_stats()
```

## Command Line Options

| Option | Description | Default |
|--------|-------------|---------|
| `path` | File or directory path to translate | `.` |
| `-o, --output` | Output file/directory path | In-place |
| `-s, --service` | Translation service (`google`, `baidu`) | `google` |
| `--patterns` | File patterns to match | All text files |
| `--no-backup` | Skip creating backup files | `False` |
| `--workers` | Maximum number of worker threads | `5` |
| `--batch-size` | Batch size for translations | `10` |
| `--rate-limit` | Rate limit between API calls (seconds) | `0.05` |

## Examples

### Basic File Translation

```bash
# Translate a Python file
ect my_script.py

# Translate with output to different file
ect input.py -o translated.py
```

### Directory Translation

```bash
# Translate all Python files in current directory
ect . --patterns "*.py"

# Translate Flutter project files
ect ./lib --patterns "*.dart" --workers 8

# Translate with custom output directory
ect ./src --patterns "*.js" "*.ts" -o ./translated_src
```

### Advanced Usage

```bash
# High-performance batch translation
ect ./project \
    --patterns "*.py" "*.dart" "*.js" \
    --workers 15 \
    --batch-size 25 \
    --rate-limit 0.01 \
    --output ./translated_project

# Translate without creating backups
ect ./docs --patterns "*.md" --no-backup
```

### Python API Examples

#### Basic Translation

```python
from enhanced_chinese_translator import EnhancedChineseTranslator

translator = EnhancedChineseTranslator()

# Translate single text
result = translator.translate_texts_batch(["你好，世界！"])
print(result[0])  # "Hello, world!"
```

#### Batch Processing

```python
# Process multiple texts efficiently
chinese_texts = [
    "这是第一个测试文本",
    "这是第二个测试文本", 
    "这是第三个测试文本"
]

translations = translator.translate_texts_batch(chinese_texts)
for original, translated in zip(chinese_texts, translations):
    print(f"{original} -> {translated}")
```

#### Directory Processing

```python
# Translate entire project
translator = EnhancedChineseTranslator(
    max_workers=10,
    batch_size=20
)

success_count = translator.translate_directory(
    './my_project',
    file_patterns=['*.py', '*.dart', '*.js'],
    output_dir='./translated_project',
    backup=True
)

print(f"Successfully translated {success_count} files")
```

## Supported File Types

The translator automatically detects and processes various file types:

- **Programming Languages**: `.py`, `.dart`, `.js`, `.ts`, `.java`, `.cpp`, `.c`, `.h`
- **Web Technologies**: `.html`, `.css`, `.scss`, `.vue`, `.jsx`, `.tsx`
- **Documentation**: `.md`, `.txt`, `.rst`, `.xml`, `.json`, `.yaml`
- **Configuration**: `.conf`, `.ini`, `.cfg`, `.properties`

## Translation Context Handling

The tool intelligently handles different contexts:

### String Literals
```python
# Before
message = "用户登录失败"

# After  
message = "User login failed"
```

### Comments
```python
# Before
# 这是一个重要的函数
def important_function():
    pass

# After
# This is an important function  
def important_function():
    pass
```

### Mixed Content
```dart
// Before
/// 获取用户信息的API接口
Future<UserInfo> getUserInfo(String userId) {
  // 发送HTTP请求
  return http.get('/api/user/$userId');
}

// After
/// API interface for getting user information
Future<UserInfo> getUserInfo(String userId) {
  // Send HTTP request
  return http.get('/api/user/$userId');
}
```

## Performance Features

### Multi-threading
- Concurrent translation processing
- Configurable worker thread count
- Thread-safe caching and rate limiting

### Batch Processing  
- Group multiple texts for efficient API usage
- Reduces API call overhead
- Optimized for large-scale translations

### Smart Caching
- Persistent translation cache
- Avoids duplicate API calls
- Thread-safe cache operations

### Rate Limiting
- Prevents API service throttling
- Configurable delay between requests  
- Per-thread rate limiting

## Configuration

### Environment Variables

```bash
# Set default translation service
export ECT_SERVICE=google

# Set default worker count
export ECT_WORKERS=8

# Set cache directory
export ECT_CACHE_DIR=/path/to/cache
```

### Configuration File

Create `~/.ect_config.json`:

```json
{
  "translation_service": "google",
  "max_workers": 8,
  "batch_size": 15,
  "rate_limit": 0.03,
  "backup": true,
  "default_patterns": ["*.py", "*.dart", "*.js"]
}
```

## Performance Statistics

The tool provides detailed performance metrics:

```
📊 Performance Statistics:
  ├─ Total translations: 1,247
  ├─ Cache hit rate: 23.4%
  ├─ API calls made: 89
  ├─ Failed translations: 0 (0.0%)
  ├─ Total processing time: 45.67s
  └─ Average time per translation: 36.6ms
```

## Troubleshooting

### Common Issues

**API Rate Limiting**
```bash
# Increase rate limit delay
ect myfile.py --rate-limit 0.1
```

**Large File Processing**
```bash
# Reduce batch size and workers
ect large_project/ --workers 3 --batch-size 5
```

**Memory Usage**
```bash
# Process files one at a time
ect project/ --workers 1 --batch-size 1
```

### Error Handling

The translator includes robust error handling:
- Network timeout recovery
- API service fallbacks  
- Partial translation recovery
- Progress preservation

## Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Setup

```bash
git clone https://github.com/enhanced-translator/enhanced-chinese-translator.git
cd enhanced-chinese-translator
pip install -e ".[dev]"
```

### Running Tests

```bash
pytest tests/
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Changelog

### Version 1.0.0
- Initial release
- Multi-threaded translation processing
- Batch translation support
- Smart caching system
- Rate limiting
- Directory processing
- Performance statistics
- Multiple translation services

## Support

- 📖 [Documentation](https://github.com/jasonlau233/enhanced_chinese_translator/wiki)
- 🐛 [Issue Tracker](https://github.com/jasonlau233/enhanced_chinese_translator/issues)
- 💬 [Discussions](https://github.com/jasonlau233/enhanced_chinese_translator/discussions)

## Acknowledgments

- Thanks to all contributors who helped improve this tool
- Inspired by the need for efficient code translation workflows
- Special thanks to the open-source translation service providers

---

**Made with ❤️ by the Enhanced Chinese Translator Team**