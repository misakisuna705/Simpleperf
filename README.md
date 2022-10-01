# Simpleperf

<!-- vim-markdown-toc GFM -->

* [bin](#bin)
    - [list](#list)
    - [stat](#stat)
        + [task](#task)
        + [cpu](#cpu)
        + [time](#time)
        + [event](#event)
    - [record](#record)
        + [rate](#rate)
        + [output](#output)
    - [report](#report)
        + [input](#input)
        + [parser](#parser)
        + [filter](#filter)
* [script](#script)
    - [record](#record-1)
        + [app_profiler.py](#app_profilerpy)
        + [run_simpleperf_on_device.py](#run_simpleperf_on_devicepy)
    - [report](#report-1)
    - [report.py](#reportpy)
    - [report_html.py](#report_htmlpy)
* [issue](#issue)

<!-- vim-markdown-toc -->

---

## bin

```zsh
simpleperf --help
```

### list

-   --show-features # ???
-   simpleperf list

### stat

-   --print-hw-counter
-   simpleperf stat [task] [cpu] [time] [event]

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
-   simpleperf record [task] [cpu] [time] [event] [rate] [ouput]

#### rate

-   -f [records/second]
-   -c [records]
-   --cpu-percent [max percents]

#### output

-   -o [path]

### report

-   -n # ???

#### input

-   -i [path]

#### parser

-   --sort [comm,pid,tid,symbol]

#### filter

-   --comms [executable, executable, ...]
-   --pids [pid, pid, ...]
-   --tids [tid, tid, ...]
-   --dsos [lib.so, lib.so, ...]

## script

### record

#### app_profiler.py

-   ./app_profiler.py # simpleperf record
-   ./app_profiler.py -r "--xxx --xxx" # simpleperf record "--xxx --xxx"

-   ./app_profiler.py -cmd [executable] # simpleperf record [executable]
-   ./app_profiler.py -p xxx.xxx.xxx # simpleperf record --app
-   ./app_profiler.py -np [process name]
-   ./app_profiler.py --pid [pid] # simpleperf record -p

-   --trace-offcpu on-cpu # ???
-   --trace-offcpu off-cpu # ???
-   --trace-offcpu on-off-cpu # ???
-   --trace-offcpu mixed-on-off-cpu # ???

#### run_simpleperf_on_device.py

### report

### report.py

-   ./report.py # simpleperf report

### report_html.py

## issue

-   [SimplePerf: Difference between Hardware events and raw events?](https://github.com/android/ndk/issues/550)
-   [[question] Finding power consumption information from simpleperf.](https://github.com/android/ndk/issues/1293)
