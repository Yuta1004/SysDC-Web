---
title: "モジュール(Module)"
date: 2022-09-23T08:44:31Z
weight: 5
---

Module は [Function]({{%relref "language/function.md"%}}) または [Procedure]({{%relref "language/procedure.md"%}}) をある一つの単位にまとめるために定義します．

### 構文

```text
module <NAME> {}

module <NAME> {
    <FUNCTION>
}

module <NAME> {
    <PROCEDURE>
}

module <NAME> {
    <FUNCTION>
    <PROCEDURE>
    ...
}
```

#### NAME

NAME は **\.** を含まない文字列です．  
ただし，既に同じ NAME をもつデータやモジュールが定義済みである場合，エラーになります．

#### FUNCTION

[Function]({{%relref "language/function.md"%}}) を参照してください．

#### PROCEDURE

[Procedure]({{%relref "language/procedure.md"%}}) を参照してください．

### サンプル

```text
unit test;

module BoxModule {
    proc test() {

    }

    func test2(a: i32) -> i32 {
        @return a
    }
}
```
