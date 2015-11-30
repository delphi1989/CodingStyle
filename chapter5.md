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

類別名稱以**大寫駝峰式字型**（**UpperCamelCase**）組成。
類別名稱多半為單純的名詞或是名詞片語，例如：Character 或 ImmutableList。介面的命名方式亦相同（如List），但有時會以形容詞或形容詞片語代替（如：Readable）

對Annotation型別而言，並沒有特定或是固有的規則去命名。

測試類別以將要被測試的類別名稱作為開頭，而以**Test**單字作結，例如：HashTest、HashIntegrationTest

>5.2.3 方法命名

方法名稱以小寫駝峰式字型（LowerCamelCase）組成。
方法的名稱通常是動詞或是動詞片語，例如：sendMessage 或 stop。

底線可能會出現在Junit的Test方法中，用來分隔方法名稱的邏輯組合。典型的格式是：
test<要被測試的方法>_<狀態>，例如testPop_emptyStack。對於test方法並沒有明確的定義如何命名。




















