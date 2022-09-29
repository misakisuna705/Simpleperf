# Simpleperf

<!-- vim-markdown-toc GFM -->

* [simpleperf](#simpleperf)
    - [list](#list)
    - [stat](#stat)
        + [task](#task)
        + [core](#core)
        + [time](#time)
        + [event](#event)
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

-   --print-hw-counter
-   simpelperf stat [task] [core] [time] [event]

#### task

-   -a
-   [executable]
-   --app [xxx.xxx.xxx] # ???
-   -p [pid, pid, pid, ...]
-   -p [pid, pid, pid, ...] --per-thread
-   -p [pid, pid, pid, ...] --per-thread --no-inherit
-   -t [tid, tid, tid, ...]

#### core

-   --per-core

#### time

-   --duration [seconds]
-   --interval [milliseconds]
-   --interval-only-values #???

#### event

-   -e [event, event, event, ...]
-   --group [event, event, event, ...]

### record

```zsh
simpleperf record --help
```

-   --use-devfreq-counters

## app_profiler.py

### record

```zsh
app_profiler.py -r "--xxx --xxx" # simpleperf record "--xxx --xxx"
```

### report

## issue

-   [SimplePerf: Difference between Hardware events and raw events?](https://github.com/android/ndk/issues/550)
-   [[question] Finding power consumption information from simpleperf.](https://github.com/android/ndk/issues/1293)
