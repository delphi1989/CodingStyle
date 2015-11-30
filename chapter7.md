# Javadoc




#### ** 7.1 格式化**

>7.1.1 通用格式

Javadoc區塊的基本格式化樣式如下：

    /** 
     * Multiple lines of Javadoc text are written here,
     * wrapped normally... 
     */
     public int method(String p1) { ... }

或是像這個單行格式化樣式的例子：

    /** An especially short bit of Javadoc. */
    
基本格式化樣式是通用的。當沒有使用Javadoc區塊、及Javadoc區塊（包含註解符號）可以使用單行就完成敘述時，單行格式化樣式可替代基本格式化樣式。  

>7.1.2 段落

在段落間或是在Javadoc標記群組之前，會有一行空行，該空行只有一個星號，沒有其他內容。除了第一個段落以外，每個段落在第一個字之前都會有```<p>```標籤，且第一字與```<p>```間沒有空白分隔

>7.1.3 @Javadoc標記

任一被使用的Javadoc標記會依照```@param、@return、@throws、@decrepated```的順序呈現，而這四個標記呈現時不會有空敘述的情況發生。當標記敘述超過一行時，接下來的敘述應相對於```@符號```(at-clause)有4個或更多space的縮排。