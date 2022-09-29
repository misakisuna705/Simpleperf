# Simpleperf

<!-- vim-markdown-toc GFM -->

* [simpleperf](#simpleperf)
    - [list](#list)
    - [stat](#stat)
        + [task](#task)
        + [event](#event)
        + [time](#time)
    - [record](#record)
* [app_profiler.py](#app_profilerpy)
    - [record](#record-1)
    - [report](#report)
* [issue](#issue)

<!-- vim-markdown-toc -->

---

## simpleperf

```zsh
simpleperf --help
```

### list

```zsh
simpleperf list

List of hw-cache events:
  branch-loads
  ...
List of hardware events:
  cpu-cycles
  instructions
  ...
List of software events:
  cpu-clock
  task-clock
  ...
```

### stat

```zsh
simpleperf stat --print-hw-counter
```

#### task

```zsh
simpleperf stat -a
simpleperf stat [executable]
simpleperf --app [xxx.xxx.xxx]
simpleperf stat -p [pid, pid, pid, ...]
simpleperf stat -p [pid, pid, pid, ...] --per-thread
simpleperf stat -p [pid, pid, pid, ...] --per-thread --no-inherit
simpleperf stat -t [tid, tid, tid, ...]
```

#### event

-   -e [event, event, event, ...]
-   --group [event, event, event, ...]

#### time

-   --duration [seconds]
-   --interval [milliseconds]

### record

```zsh
simpleperf record --help
```

```zsh
simpleperf record --use-devfreq-counters
```

## app_profiler.py

### record

```zsh
app_profiler.py -r "--xxx --xxx" # simpleperf record "--xxx --xxx"
```

### report

## issue

-   [SimplePerf: Difference between Hardware events and raw events?](https://github.com/android/ndk/issues/550)
-   [[question] Finding power consumption information from simpleperf.](https://github.com/android/ndk/issues/1293)
