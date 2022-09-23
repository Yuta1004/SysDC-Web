---
title: "Logger"
date: 2022-09-23T15:05:28Z
weight: 2
---

### コマンド

```text
./sysdc parse logger.def string.def io.def time.def
```

### logger.def

```text
unit logger;

from std import String;
from std.io import IO;
from std.time import TimeStamp, Time;

module Logger {
    proc info(msg: String) {
        @affect IO.stdout(msg)

        @modify msg {
            use timestamp;
        }

        @spawn timestamp: TimeStamp {
            let now = Time.getNowTime();
            return now;
        }
    }

    proc error(msg: String) {
        @affect IO.stdout(msg)

        @modify msg {
            use timestamp;
        }

        @spawn timestamp: TimeStamp {
            let now = Time.getNowTime();
            return now;
        }
    }
}
```

### string.def

```text
unit std;

data String {}
```

### io.def

```text
unit std.io;

module IO {
    proc stdout(msg: String) {}
}
```

### time.def

```text
unit std.time;

data TimeStamp {}

module Time {
    func getNowTime() -> TimeStamp {
        @return now
        @spawn now: TimeStamp
    }
}
```
