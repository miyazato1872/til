# 「Hello World」と表示させるミニアプリを作成

- ウェブアプリのフレームワークとして、「Spring Boot」を使用していく
- 作成手順を記載していく



## アプリの雛形を作成
### Spring Bootの新規プロジェクトを作成 (Railsにおけるターミナルで「rails new」の実行)
① 専用サイトで、プロジェクトファイルを作成する https://start.spring.io/   
② プロジェクトファイルをダウンロードする   
③ ダウンロードしたファイルをIntelliJで読み込む   


|フォルダ名|用途|
|----|----|
|java|Javaのコードを格納しておく場所|
|resources|ビューのためのHTML・CSSを格納|


- ルートフォルダ（firstappフォルダ）にあるbuild.gradleは、RailsでいうGemfileに似た役割がある

### アプリの実行・停止方法

- 最初、アプリを実行するために「FirstAppApplication」ファイルを右クリックして、実行を選択した。　　　　
プロジェクトを初めて実行するときのみ、この方法で実行する。この操作によって、実行方法に関する設定が自動的に行われる。

- ２回目以降にアプリを実行する際は、画面右上にある「実行」ボタンをクリックでOK


- アプリを実行している状態でコードを変更した場合は、「再実行」ボタンをクリックする必要がある   
    
- アプリを停止する際は、実行の3つ右くらいの「停止ボタン」をクリックする

### Javaでは、コントローラーの命名で複数形にする必要はない
- Rubyの場合は「PostsController」
- Javaでは「PostController」



## アノテーション「注釈」
**アノテーションは、クラスやメソッドに特別な意味を持たせるための機能**   
「@」で始まる文字


###  @Controller
- @Controllerは、そのクラスがコントローラーであることをSpringに伝えるためのアノテーション    
「PostControllerクラス」の直前に「@Controller」
```java
@Controller
public class PostController {

}
```
Railsでは、「rails g controller」というコマンドを実行することでコントローラーを作成できた。    
Springでは、クラス定義の直前に「@Controller」と記述することで、クラスがコントローラーとして扱われるようになる
```java
@Controller
public class PostController {

}
```
Spring Bootのアプリ実行時にコンポーネントスキャンという処理が行われますが、スキャン中にアノテーションを発見すると、それが付けられたクラスに対して必要な事前準備が行われる仕組み



###  @GetMapping
- GetMappingは、ブラウザで入力されたURLと、実行されるメソッドを紐づけるためのアノテーション.    

Railsで、routes.rbファイルに記述したルーティングと同様の機能。    

Springの場合
```java
@GetMapping("/hello")
@ResponseBody
public String showHello(){

}
```
Railsのルーティング
```ruby
  get 'posts', to: 'posts#index'
```
メソッドの前に、「@GetMapping("/hello")」というアノテーションをつけることで、URLに「（アプリのルートパス）/hello」と入力された場合、そのメソッドが実行されるようになる    

@GetMappingはHTTPメソッドとして「GET」が送信された場合のアノテーション。似たものとして、後で学習する「@PostMapping」がある。

###  @ResponseBody
- @ResponseBodyは、ブラウザからのリクエストに対して、直接HTMLを返す際に利用するアノテーション。　　　　　
通常あまり使用されることはないので、以降は一般的な記述方法に置き換えていく


```java
@Controller
public class PostController {
    @GetMapping("/hello")
    @ResponseBody
    public String showHello(){
        return "<h1>Hello World!</h1>";
    }
}
```
上記のコードは以下の意味になる
- PostContorllerクラスは、コントローラーとして扱われる
- このコントローラー内で、「(アプリのルートパス)/hello」とURLが入力されたら「showHello()メソッド」が実行されるよう設定されている


showHello()メソッドの中身について確認
```java
public String showHello(){
    return "<h1>Hello World!</h1>";
}
```
showHello()の前に、「String」と記述　=>　返り値が「文字列」のメソッド　　　　　　　　　  
showHello()メソッドは、実行すると<h1>Hello World!</h1>という文字列を返すメソッド。     
この文字列がHTMLとして解釈され、ブラウザに表示される仕組み


# テンプレートエンジン
RailsではERBというテンプレートエンジンを使用してRubyのコードをビューに埋め込みし、このERBを使用することで、コントローラーとビューのコードを分離して管理しやすくすることができていた。　　　　

似たものとして、Spring BootにはThymeleafタイムリーフというライブラリがある

## Thymeleaf(タイムリーフ)
1. 「build.gradle」ファイルに記述を行って導入する。(RailsのGemfileに似た役割のファイル)
2. firstapp/src/main/resources/templates フォルダを右クリック。メニューの中から、「新規」「HTMLファイル」を選択。　例として　　「hello.html」とし、ファイル名を入力したらエンターキー
3. 作成したHTMLファイルを編集
```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<h1>Hello World from Thymeleaf!</h1>
</body>
</html>
```

### コントローラーを変更
コントローラーからHTMLファイルを読み込めるようにする。

src/main/java/in.techcamp.firstapp/PostController.java
```java
package in.techcamp.firstapp;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;
//import org.springframework.web.bind.annotation.ResponseBody;

@Controller
public class PostController {
    @GetMapping("/hello")
//    @ResponseBody
    public String showHello(){
        return "hello";
    }
}
```
※本来は削除でいいが、分かりやすくコメントアウトにしている。


元々10行目に記述されていた@ResponseBodyは不要なので削除。


同時にインポートも不要になるので、import org.springframework.web.bind.annotation.ResponseBody;の記述も削除。

## Thymeleafの使い方を確認.   
2つの作業が必要。　　     
① 表示させるためのHTMLを作成する.  
② コントローラーから①のファイルを読み込めるようにする.  


今回はHTMLファイルに固定の文字列を記述していますが、RailsのERBファイルにRubyのコードを埋め込むことができたように、Thymeleafを使うとJavaのコードを埋め込むことができる

```java
@Controller
public class PostController {
    @GetMapping("/hello")
    public String showHello(){
        return "hello";
    }
}
```
return "hello";の部分で、表示させるHTMLファイルの名称を指定している。   
「hello.html」を呼び出したい場合、「.html」部分は省略可能.  
return "hello";と記述することで、「templates」フォルダにある「hello.html」を呼び出すことができる


# Thymeleafで変数を使う

src/main/java/in.techcamp.firstapp/PostController.java
```java
package in.techcamp.firstapp;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class PostController {
    @GetMapping("/hello")
    public String showHello(Model model) {
        var sampleText = "サンプルテキスト";
        model.addAttribute("sampleText", sampleText);
        return "hello";
    }
}
```
ビューのコードを変更.   
src/main/resources/templates/hello.html
```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<h1>Hello World from Thymeleaf!</h1>
<p th:text="${sampleText}"></p>
</body>
</html>
```

Sping Bootの場合は、Model型のオブジェクトを使用して、以下の流れで変数を渡します。    
(Railsでコントローラーからビューに変数を渡す場合は、コントローラーでインスタンス変数に値を代入していた).  

① コントローラーの引数でModelオブジェクトを受け取る.  
② Modelオブジェクトに、ビューで表示させたいデータを追加する.  
③ ビューでModelオブジェクトのデータを読み込む.  


以下のようにshowHelloメソッドの仮引数に「Model model」と指定することで、Modelオブジェクトを受け取ることができます。このオブジェクトの変数名は、modelとすることが一般的
```java
@GetMapping("/hello")
public String showHello(Model model){

    // 省略

}
```
続いて以下のコードでmodelにデータを追加
```java
@GetMapping("/hello")
public String showHello(Model model){
    var sampleText = "サンプルテキスト";
    model.addAttribute("sampleText", sampleText);
    return "hello";
}
```
model.addAttribute("sampleText", sampleText);のaddAttributeが追加を行うためのメソッド。    
- 引数にsampleTextが２回出てくることの解説
１つ目の引数では、ビューで読み込む際の名称を指定しています。ダブルクォーテーションで囲んで文字列として指定する必要があることに注意しましょう。   

２つ目ではmodelに追加したいデータを指定しています。直前の行でvar sampleText = "サンプルテキスト";と記述していますが、ここではこのsampleTextを指定しています。    

Rubyでハッシュを利用する際はキーとバリューを指定しますが、それに似たものと捉えると分かりやすいかもしれません。　　　


### ビューでの良い子見方を確認.   
<p th:text="${sampleText}"></p>


Thymeleafのth:textを使用すると、「表示したいテキスト」を任意の内容に置き換えることができます。   
   
ここではth:text="${sampleText}"と記述することで、「表示したいテキスト」の箇所を「sampleText」の内容に置き換えています。   
   
コントローラーで、sampleTextに「サンプルテキスト」という文字列を設定しているので、置き換えた後は以下のように記述したのと同じ結果になります。   
   
<p>サンプルテキスト</p>


```java
package in.techcamp.firstapp;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class PostController {
    @GetMapping("/hello")
    public String showHello(Model model) {
        var sampleText = "サンプルテキスト";
        model.addAttribute("sampleText", sampleText);
        return "hello";
    }

    @GetMapping
    public String showList(){
        return "index";
    }
}
```
@GetMappingとアノテーションの記述を行なっていますが、これは@GetMapping("/")と書くのと同じ意味です。ルートパス（/）を指定する場合の("/")は省略可能です。
