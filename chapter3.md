# 三、原始碼結構

原始碼由以下幾個結構依序組成：

1. 著作權或版權資訊（有必要的話）
2. Package敘述
3. Import敘述
4. 一個頂層類別(**top-level class**)

結構間以一列空白行分隔

#### **3.1 著作權或版權資訊**

若檔案內需要有著作權或版權資訊時，必須呈現在原始碼檔案的最上方





---

#### **3.2 Package 敘述**

package敘述不進行***line-wrapper***，也就是不換行的意思。字元數限制不適用於package敘述。
>line-wrapper：原本只會有一行的程式敘述，為了不超過字元數的限制而分隔成很多行。通常一行程式敘述應介於80 ~ 100個字元數間。



---
#### **3.3 Import 敘述**

>3.3.1 不使用通用符號import (No wildcard imports)

不使用通用符號(```*```)或static import。

>3.3.2 不進行line-wrapper (No line-wrapping)

import敘述不進行***line-wrapper***，也就是不換行的意思。字元數限制不適用於import敘述。

>3.3.3 排序與間隔

所有的import敘述會組合成不同的群組，群組間以空白行做為分隔。