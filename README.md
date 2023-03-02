# merchant_tagging

EDA – Exploratory Data Analysis

Original Dataset:
- Original dataset: (2280287 rows, 16 columns)
- Correlation Analysis: amount and txn_desc2 are highly correlated with merchant names

Unknown Merchants Dataset:
- Unknown merchants dataset: (1146663 rows, 16 columns)

Known Merchants Dataset:
- Known merchants: 1133623 rows
- Merchant name occurrence in txn_desc1 column: 413691 times
- Merchant name occurrence in txn_desc2 column: 858738 times
- Merchant name occurrence in both columns:  138,806 times -> (1133623 – (413691 + 858738))
- Total of unique known merchants: 1793
- Merchant names NOT in the CONCATENATED Transaction description: 15312
- Merchant names in the CONCATENATED Transaction description: 1118311
- Merchants only in col_1: (1118311 – 858738) = 259,573 (ONLY IN COL 1)
- Merchants only in col_2: (1118311 – 413691) = 704,620 (ONLY IN COL 2)
- Merchants in col_1 and col_2: (704,620 + 259,573) = 964,193 (COL 1 + COL 2)
- Merchants NOT in cols: 15312 (NOT IN COLS)
- Merchants Both_cols & Not in cols: (1118311 - 964,193) = 154,118 (BOTH COLS AND NOT IN COLS)
- Merchants in Both cols: (154,118 – 15312) = 138,806 (BOTH COLS)


Payment Agents VS Merchant:
- Number of payment agents: 15
- Number of transactions with known payment agents: 39166
- Same merchants names and payments agents: 21075
- Different merchants and payment agents: 18091
