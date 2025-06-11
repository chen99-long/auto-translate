# auto-transform

一个简单的腾讯翻译君 API 封装库，支持多种语言之间的互译。

## 安装

```bash
npm install chen99-easy-translate
```

## 使用方法

```typescript
import { translateAPI, supportedLanguages } from 'auto-transform';

// 基本用法 - 中文翻译成英文
async function translateToEnglish() {
  const result = await translateAPI('好好学习天天向上');
  console.log(result); // 输出翻译结果
}

// 指定源语言和目标语言
async function translateCustom() {
  const result = await translateAPI('Hello World', {
    from: 'en',
    to: 'zh'
  });
  console.log(result); // 输出中文翻译
}

// 使用 Promise
translateAPI('こんにちは', { from: 'ja', to: 'en' })
  .then(result => {
    console.log(result);
  });
```

## 支持的语言

该库支持以下语言之间的互译：

- 中文 (zh)
- 英语 (en)
- 日语 (ja)
- 韩语 (ko)
- 法语 (fr)
- 德语 (de)
- 西班牙语 (es)
- 意大利语 (it)
- 俄语 (ru)
- 葡萄牙语 (pt)
- 越南语 (vi)
- 印尼语 (id)
- 泰语 (th)
- 马来语 (ms)

## API

### translateAPI(text: string, options?: TranslateOptions): Promise<string>

将文本从一种语言翻译成另一种语言。

参数：
- `text`: 要翻译的文本
- `options`: 可选的翻译选项
  - `from`: 源语言代码（默认为 'zh'）
  - `to`: 目标语言代码（默认为 'en'）

返回：
- Promise<string>: 翻译后的文本

### supportedLanguages

包含所有支持的语言及其对应的中文名称。

## 注意事项

- 该库使用腾讯翻译君的 API
- 如果翻译失败，将返回原始文本
- 建议在翻译前检查语言代码是否在支持列表中 