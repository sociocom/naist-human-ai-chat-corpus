# NAIST 人間-AI チャットコーパス

Discord上で収集した、日本語の人間-AIマルチパーティ対話コーパスです。
「幸福とは何か、どのように幸福を実現できるのか」をテーマとして、人間1名と4体のAIエージェントが対話しています。各メッセージには、談話行為ラベルを付与しています。

## コーパス概要

| 項目 | 値 |
|---|---:|
| 対話数 | 103 |
| メッセージ数 | 11,232 |
| 1対話あたりの平均メッセージ数 | 108.9 |
| 人間の平均メッセージ数 | 29.1 |
| AIの平均メッセージ数 | 79.8 |

AIエージェントには `gemini-2.0-flash` を使用しています。

## データ形式

csv形式で、1つの対話を1つのファイルに収録しています。

| 列名 | 内容 |
|---|---|
| `message_id` | メッセージID |
| `speaker` | 発話者．`human`は人間の実験参加者，`カナコ`，`アユ`，`カズキ`，`ケン`はそれぞれペルソナを設定されたAI．`system`は実験進行のためにシステムから固定文面で送信されたメッセージ． |
| `created_at` | 投稿日時 |
| `content` | メッセージ本文 |
| `is_reply` | 返信メッセージかどうか |
| `reply_to_message_id` | 返信先のメッセージID |
| `reply_depth` | 返信の深さ |
| `Level1` | 談話行為ラベル（複数ラベルの場合はカンマ区切り） |

## 談話行為ラベル


| カテゴリ| タグ |
|---|---|
| タスク系 | `T_Inform`, `T_Agreement`, `T_Disagreement`, `T_Question`, `T_CheckQuestion`, `T_Answer`, `T_Request`, `T_A-Request` |
| 社会的付き合い管理系 | `S_Greeting`, `S_Apology`, `S_A-Apology`, `S_Thanking`, `S_A-Thanking` |
| フィードバック系 | `FB_Auto_Positive`, `FB_Allo_Positive`, `FB_Auto_Negative`, `FB_Allo_Negative`, `FB_Repetition` |
| Qualifier系 | `Q_Sentiment_Positive`, `Q_Sentiment_Negative` |

## 匿名化と利用上の注意

- 人間参加者のユーザーIDは `user` に置換しています。
- 本コーパスには、人間および生成AIによる自由記述の発話が含まれます。
- 研究・分析に使用する際は、個人の再同定や参加者に不利益を与える利用を行わないでください。

## Citation

本コーパスを利用した研究成果では、次の論文を引用してください。

```
@article{nagai2026construction,
  author = {永井 宥之 and 伊藤 和浩 and 白石 暖哉 and 山崎 由佳 and 若宮 翔子 and 荒牧 英治},
  title = {話行為がアノテーションされた人間-AI対話コーパスの構築},
  journal = {言語資源ワークショップ2026}
  year = {2026},
}
```

