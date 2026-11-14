# 参与贡献 / Contributing

这个仓库欢迎新的语言和变体。会话流程在 `skills/language-coach/SKILL.md`，每种变体一个文件。两边不要搅在一起。

New languages and varieties are welcome. The session flow lives in `skills/language-coach/SKILL.md`. Each variety is one file. Keep those layers apart.

## 新增一种变体

1. 复制 `skills/language-coach/variants/_TEMPLATE.md`。
2. 保存为 `skills/language-coach/variants/<id>.md`。`<id>` 用稳定的短标签，例如 `en-US`、`ja-JP`、`es-MX`。文件名区分大小写，请与文件内的 `id` 一致。
3. 写上 `also_called`，包含学习者真的会说的名字，以及简体中文里的叫法。教练靠文件名、`id` 和 `also_called` 选择文件。
4. 填完模板里的每一节：书写、词汇、日常表达、语法与用法、发音、一致性。规则要具体，能让教练当场做出选择。
5. 不要改 `SKILL.md`，也不要在别的文件里登记一张“官方变体清单”。目录本身就是清单。以 `_` 开头的文件不会被当成可供选择的变体。
6. 若你希望 README 的简介里提到这个新文件，可以改 README。那是给人看的，不是教练加载变体的条件。

发音请写明你采用的教学口音，并写明同一语言里其他合法口音不是错误。相邻变体的合法形式（另一种拼写、另一个常用词、另一种同样标准的语法）默认不判错，除非学习者要求严格统一。这一点写进该文件的一致性一节。

不要把流程写进变体文件。什么时候纠正、如何保存词汇、六段复习、逐句跟读，都已经在 `SKILL.md` 和 `references/` 里。

## Add a variant

1. Copy `skills/language-coach/variants/_TEMPLATE.md`.
2. Save it as `skills/language-coach/variants/<id>.md`. Use a stable short id such as `en-US`, `ja-JP`, or `es-MX`. Filenames are case-sensitive and must match the `id` inside the file.
3. Fill `also_called` with names a learner will actually say, including the Simplified Chinese name. The coach chooses a file by filename, `id`, and `also_called`.
4. Complete every section: writing system, vocabulary, everyday expressions, grammar and usage, pronunciation, consistency. Make the rules concrete enough to apply in a live turn.
5. Do not edit `SKILL.md`, and do not add a registry of official variants anywhere else. The directory is the registry. Files whose names start with `_` are not offered as varieties.
6. You may mention the new file in the README. That list is for humans. The coach does not need it in order to load the file.

Name the teaching accent, and say that other legitimate accents of the same language are not errors. A standard form from a neighboring variety — another spelling, a different everyday word, another standard construction — stays unmarked unless the learner asked for strict consistency. Put that in the file's consistency section.

Do not put session flow in a variant file. When to correct, how vocabulary is saved, the six-part review, and sentence-by-sentence shadowing already live in `SKILL.md` and `references/`.

## 解释语言

解释语言是学习者的设置，默认 `zh-CN`，写在 `knowledge-base/learner-profile.md`。变体文件不要规定解释语言。练习始终使用变体所属的目标语言。

## Explanation language

The explanation language is a learner setting, `zh-CN` by default, stored in `knowledge-base/learner-profile.md`. Variant files do not set it. Practice stays in the variety's target language.

## 文字与许可

用你自己的话写规则。不要从其他教练技能整段搬文案。

贡献以 MIT 发布。提交即表示你同意按仓库根目录的 [LICENSE](LICENSE) 授权，并保留其中 Prof. Shihmin Lo 的原版权声明与许可文本。详见 [NOTICE](NOTICE)。

## Wording and license

Write the rules in your own words. Do not paste passages from another coaching skill.

Contributions are released under the MIT License. By submitting, you agree to license your contribution under the repository [LICENSE](LICENSE), which also retains Prof. Shihmin Lo's original copyright notice and permission text. See [NOTICE](NOTICE).
