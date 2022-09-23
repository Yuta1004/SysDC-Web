---
title: "名前"
date: 2022-09-23T09:09:02Z
weight: 2
---

SysDC で定義されたすべての要素は名前を持ちます．

- [Unit]({{%relref "language/unit.md"%}}) 
- [Module]({{%relref "language/module.md"%}}) 
- [Data]({{%relref "language/data.md"%}}) 
- (など…)

名前は以下に示すような **\.** で区切られた文字列です．  
すべての名前は **.0** を先頭に持ちます．

- .0
- .0.test.Test
- .0.test.TestModule
- .0.test.TestModule.func_a

### サンプル

以下のサンプルプログラム内において，各要素は次のような名前を持ちます．  

```text
unit box;  → .0.box

data Box { → .0.box.Box
    x: i32,  → .0.box.Box.x
    y: i32   → .0.box.Box.y
}

module BoxModuleA {  → .0.box.BoxModuleA
    proc test() {  → .0.box.BoxModule.test
        @spawn a: i32 { → .0.box.BoxModuleA.test.a

        }
    }
}

module BoxModuleB { }

```

(上のプログラムは正常に変換できません)
