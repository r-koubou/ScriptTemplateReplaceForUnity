## Unity: 新規作成スクリプト・マクロ展開拡張機能

### 概要

新規にスクリプトファイルを作成する時に参照されるスクリプトテンプレートファイルにマクロを記述しておき
スクリプトファイル新規作成時に指定の文字列に展開する機能を提供するエディタ拡張。


Unityのデフォルトでは

* \#SCRIPTNAME\#

をスクリプトファイル名に展開するが、それ以外の以下の項目を展開する追加機能を提供する。

* 年 yyyy（#YEAR#）
* 日付 yyyy/mm/dd（#DATE#）
* 名前（#MY_NAME#）
* 組織名（#MY_COMPANY#） 
* 名前空間（#NAMESPACE#）


### インストール

#### 1 スクリプトファイルの設置

ScriptTemplateReplace.cs を任意の Editor フォルダ以下に設置する

#### 2 スクリプトファイルの編集

ScriptTemplateReplace.cs を開き、以下の箇所の変数の文字列を任意のテキストに書き換える

~~~cs
/** using for "#NAME#" replacement */
static readonly string MY_NAME          = "Your Name";

/** using for "#MY_COMPANY_NAME#" replacement */
static readonly string MY_COMPANY_NAME  = "Your Company";

/** using for "#NAMESPACE#" replacement */
static readonly string NAMESPACE        = "com.example.myapp";
~~~

#### 3 テンプレートファイルの編集

Unityのスクリプトテンプレートファイルを編集する。

 * Windows: $(UNITY)/Resources/ScriptTemplate/
 * macOS: Unity.app/Contents/Resources/ScriptTemplates/


### 項目の追加

ScriptTemplateReplace.cs に処理を追加することで拡張可能

参考：[How To Customize Unity Script Templates (support.unity3d.com)](https://support.unity3d.com/hc/en-us/articles/210223733-How-to-customize-Unity-script-templates)
