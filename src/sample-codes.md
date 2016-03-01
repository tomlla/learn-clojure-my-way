# Sample Codes

## Hello World

```clj
(println "hello world")

```
## ネームスペース内ローカル変数
> 他に良い呼び方があるかもしれません

```clj
(def name "tomlla")
```

## 関数定義
```clj
(defn helloworld (println "Hello World!"))
(defn greet [name] (println "Hello! " name))
```

## 関数呼出
```clj
(helloworld) ; "Hello World!"
; ちなみに "カンマ;" はコメント
(greet "@tomlla") ; "Hello! @tomlla"

(def isGranditProductCode? (fn [^String code] (= (count code) 10)))
(isGranditProductCode? "x") ; false
(isGranditProductCode? "1234567890") ; true 
```

## 条件分岐
```clj
(defn toybox [n] (if (even? n) "woman" "man"))
(defn fzbz [n]
    (cond 
        (= (mod n 15) 0) "fizzbuzz"
        (= (mod n 3) 0) "fizz"
        (= (mod n 5) 0) "buzz"))
```

## data structures
```clj
; list 
'(a b c d)

; map(array-map) 
{:age 22 :birth-day "1993.7.30"}

; vector 
[1 2 3 4]

; set 
#{a b c}

; listの中のmap
[ {:age 22 :birth-day "1993.7.30"} 
  {:age 23 :birth-day "1992.1.30"}]
```

## 文字操作
```clj
(str ":" "emacs") 
(format "name: %s age: %d" "tomlla" 24) ; "name: tomlla age: 23"
```

## コレクション操作 & thread macro
```clj
(filter even? [2 3 4])
; > (2 4)

(map #(* % %) (filter even? [2 3 4]))
; > (4 16)

(->> [2 3 4]
     (filter even?)
     (map #(* % %)))
; > (4 16)
```

# javaを呼びだして使う
```clj
; オブジェクト生成　
(new java.util.Date)

; メソッド呼び出し  (めそっど オブジェクト 引数...)
(.equals (new Long "1") 1) ; true
(.equals (new Integer "1") 1) ; false
```

## 省略記法

```clj
; オブジェクト生成省略記法版
(java.util.Date.) ;

; メソッド呼び出し省略記法版
(. (java.uti.Date.) toString)
```

## 例外を投げる
```clj
(throw (Exception. "throw from leiningen repl"))
```


## クラスっぽいなにかやjavaのクラスをclojureから作成するにはこちらを参考にしてください
http://cemerick.com/2011/07/05/flowchart-for-choosing-the-right-clojure-type-definition-form/
