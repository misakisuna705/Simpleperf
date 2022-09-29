# Simpleperf

<!-- vim-markdown-toc GFM -->

* [simpleperf](#simpleperf)
    - [list](#list)
    - [stat](#stat)
        + [task](#task)
        + [cpu](#cpu)
        + [time](#time)
        + [event](#event)
    - [record](#record)
        + [rate](#rate)
        + [output](#output)
* [app_profiler.py](#app_profilerpy)
    - [record](#record-1)
        + [task](#task-1)
    - [report](#report)
* [issue](#issue)

<!-- vim-markdown-toc -->

---

## simpleperf

```zsh
simpleperf --help
```

### list

-   --show-features # ???
-   simpleperf list

### stat

-   --print-hw-counter
-   simpelperf stat [task] [cpu] [time] [event]

#### task

-   -a
-   [executable]
-   --app [xxx.xxx.xxx] # ???
-   -p [pid, pid, pid, ...]
-   -p [pid, pid, pid, ...] --per-thread
-   -p [pid, pid, pid, ...] --per-thread --no-inherit
-   -t [tid, tid, tid, ...]

#### cpu

-   --trace-offcpu # ???
-   --per-core

#### time

-   --duration [seconds]
-   --interval [milliseconds]
-   --interval-only-values # ???

#### event

-   -e [event, event, event, ...]
-   --group [event, event, event, ...]

### record

-   --help
-   --use-devfreq-counters
-   simpelperf record [task] [cpu] [time] [event] [rate] [ouput]

#### rate

-   -f [records/second]
-   -c [records]
-   --cpu-percent [max percents]

#### output

-   -o [path]

## app_profiler.py

### record

-   app_profiler.py -r "--xxx --xxx" # simpleperf record "--xxx --xxx"

#### task

-   -p xxx.xxx.xxx.xxx # ???

### report

## issue

-   [SimplePerf: Difference between Hardware events and raw events?](https://github.com/android/ndk/issues/550)
-   [[question] Finding power consumption information from simpleperf.](https://github.com/android/ndk/issues/1293)
