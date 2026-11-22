# Thesis Template Apply — Demo Pack

Synthetic test files for the **thesis-template-apply** skill. No real student
data, no real university template, no school logo or watermark.

| File | What it is |
|---|---|
| `demo-template.docx` | Tokenized template: 範例大學 / 企業管理系行銷與流通管理碩士班 / 碩士論文. Contains `{{TITLE}}` … `{{BODY}}`. |
| `demo-thesis.docx` | Thesis body: five chapters, two tables, one figure, six references, appendix. No front matter, no tokens. |
| `expected-output.pdf` | 16-page result: Chinese and English covers, approval page, 致謝, 摘要, ABSTRACT, 目錄, 表目錄, 圖目錄, body 1–7. |

## How to test

1. Download the three files into one folder.
2. In your agent, use the skill and give the files **in this order**:
   - first: `demo-thesis.docx`
   - then: `demo-template.docx`
3. Cover metadata:

   ```text
   中文題目：服務品質、顧客滿意度與顧客忠誠度關係之研究
   英文題目：The Relationship among Service Quality, Customer Satisfaction, and Customer Loyalty
   研究生：王小明 / Wang Xiao-Ming
   指導教授：陳大文 / Chen Da-Wen
   日期：115 年 6 月 / June 2026
   ```

4. Compare the new PDF with `expected-output.pdf`: 16 pages, 24 TOC entries,
   2 table entries, 1 figure entry.

## What this pack is not

It is a demo, not a university-template service. For a real thesis, use your own
school's official `.docx` and tokenize it once:

- replace eight cover samples with `{{TITLE}}`, `{{TITLE_EN}}`, `{{NAME}}`,
  `{{NAME_EN}}`, `{{ADVISOR}}`, `{{ADVISOR_EN}}`, `{{DATE}}`, `{{DATE_EN}}`;
- add one `{{BODY}}` paragraph at the end.

See the skill README → “Tokenize your school template”. A template without these
tokens can still rebuild the body, catalogs and numbering, but its cover will not
be filled automatically.

## Verified result

```text
RESULT=PASS
PAGES=16
TOC_ENTRIES=24
TABLE_ENTRIES=2
FIGURE_ENTRIES=1
TABLES=2
CAPTIONS=3
REFERENCES=6
```
