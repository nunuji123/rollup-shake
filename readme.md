# rollup-shake

## 现象

### 现象 - ESM1

a.js

```javascript
export const a = 'color red'
export const aa = 'color red color'
```

index.js

```javascript
import { a } from './src/a'

console.log('a :>> ', a)
```

bundle.js

```javascript
'use strict'

const a = 'color red'

console.log('a :>> ', a)
```

结论： 完全没有 aa 常量，使用了 ES6 的 import 功能，根本就没引入
如果是 cjs 呢？

## 如何抖动的呢？
