JETT - Java Excel Template Translator
----------------

JETT can be found online at http://jett.sourceforge.net.

Description
----------------

JETT is Java Excel Template Translator.  Give it a Map of "beans" -- mapping  
variable names to your own data objects, specify a pre-existing Excel template  
file, and JETT will create a new Excel spreadsheet, populating your data into  
it.  The data can come from any source.  Mark up your template spreadsheet  
first, with JEXL Expressions (e.g. "${myVariable}") and XML-like Tags (e.g.  
<jt:forEach items="${myList}" var="item">) for control over how JETT translates  
your template spreadsheet and populates your data.  You can even create your  
own Tags to implement custom processing logic.  JETT works with .xls and .xlsx  
Excel files.  

Example
----------------

Here is a quick example of how to use JETT:  

- Excel template spreadsheet:

+----------------+----------------+  
|${var}          |${var2}!        |  
+----------------+----------------+  

- Java code to use JETT:

```
Map<String, Object> beans = new HashMap<String, Object>();
beans.put("var", "Hello");
beans.put("var2", "World");
ExcelTransformer transformer = new ExcelTransformer();
try
{
   transformer.transform("template.xlsx", "result.xlsx", beans);
}
catch (IOException e)
{
   System.err.println("I/O error occurred: " + e.getMessage());
}
catch (InvalidFormatException e)
{
   System.err.println("Spreadsheet was in invalid format: " + e.getMessage());
}
```

- The resultant Excel spreadsheet:

+----------------+----------------+  
|Hello           |World!          |    
+----------------+----------------+  

Installation
----------------

JETT を使用するには、以下から最新のディストリビューションをダウンロードできます。  
唯一のモジュールは「jett-core」です。  
「jett-core」jar ライブラリをクラスパスに配置します。  

Build Instructions
----------------

JETT を自分で構築したい場合は、次の手順を実行します。  
1. ソースコードを取得します。  
   ａ． JETT の最新ディストリビューションを次からダウンロードします。  
      http://sourceforge.net/projects/jett/files/。  
      これには、最新リリースのソース コードが含まれています。  
   または  
   b. Subversion を使用してトランクから最新のソース コードをチェックアウトします。  
      Subversion URL http://svn.code.sf.net/p/jett/code-0/trunk  

2. http://maven.apache.org/ から Maven 2 以降を入手してインストールします。  

3. Maven を実行して JETT をビルドします。  
    mvnクリーンインストール  

Licensing
----------------

https://github.com/furukawatts/jett/blob/master/LICENSE  
