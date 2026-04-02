---
tags: [map]
---

# Writing MAP

## 全記事
```dataview
TABLE status, genre, file.mtime AS "更新"
FROM "Writing"
SORT status ASC, file.mtime DESC
```

## ジャンル別

### 恋愛・パートナー
```dataview
LIST FROM "Writing" WHERE contains(genre, "romance")
```

### 人生・体験
```dataview
LIST FROM "Writing" WHERE contains(genre, "life")
```

### 哲学・自己探求
```dataview
LIST FROM "Writing" WHERE contains(genre, "philosophy")
```

### ビジネス・仕事
```dataview
LIST FROM "Writing" WHERE contains(genre, "business")
```

### 旅
```dataview
LIST FROM "Writing" WHERE contains(genre, "travel")
```
