# 命名方式

#### **5.1 識別字串通用的規則**

識別字（物件參考）只利用ASCII字元及數字來表示，或如下所舉的例子，使用底線。因此每個有效的識別字都能在正則表達式中以```\w+``` 去配對

在Google Style中，特別的前綴或後綴，像是在下面的例子中：

```name_ , mName , s_name and kName```皆不使用

#### **5.2 不同類型的識別字串規則**

>5.2.1 Package命名

package的名稱皆由小寫字母構成，由不同的單字串接起來（不使用底線）。例如：```com.example.deepspace```是正確的，
而不使用 ```com.example.deepSpace``` 或 ```com.example.deep_space```

>5.2.2 類別命名
























