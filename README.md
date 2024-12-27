# Terminal Benchmark

Benchmarks of several popular terminal emulator. All test is done on 
newest version (at the time of writing) with default config. Check respective 
directory to see test on each terminal. 

> Tested on older hardware, margin of results might be smaller in newer ones.

<details>
<summary>System Specification</summary>

```txt
Host: 2350B67 (ThinkPad T430)
OS: Arch Linux x86_64
Kernel: Linux 6.12.6-arch1-1
WM: Hyprland (Wayland)
Shell: zsh 5.9
CPU: Intel(R) Core(TM) i7-3632QM (8) @ 3.20 GHz - 48.0°C
GPU: Intel 3rd Gen Graphics Controller @ 1.15 GHz [Integrated]
Memory: 15.44 GiB
```

</details>

## Input Latency

| run | alacritty |  foot | ghostty |       kitty | wezterm |
|----:|----------:|------:|--------:|------------:|--------:|
|   1 |     35.45 | 36.90 |   36.62 |       35.22 |   66.18 |
|   2 |     35.03 | 37.32 |   35.89 |       34.89 |   65.98 |
|   3 |     35.46 | 37.39 |   36.33 |       35.06 |   66.74 |
|   4 |     35.92 | 36.71 |   36.13 |       35.10 |   65.06 |
|   5 |     35.98 | 37.86 |   36.52 |       34.88 |   63.82 |
| avg |     35.57 | 37.24 |   36.30 | **_35.03_** |   65.56 |

> Lower is better

Measured in miliseconds(ms) using [zsh-prompt-benchmark](https://github.com/romkatv/zsh-prompt-benchmark).

## Plaintext IO

| run | alacritty |      foot | ghostty | kitty | wezterm |
|----:|----------:|----------:|--------:|------:|--------:|
|   1 |       284 |        97 |     310 |   152 |    1421 |
|   2 |       319 |       104 |     295 |   147 |    1643 |
|   3 |       314 |       107 |     296 |   142 |    1322 |
|   4 |       298 |        95 |     292 |   145 |    1609 |
|   5 |       278 |       100 |     311 |   143 |    1473 |
| avg |       299 | **_101_** |     301 |   146 |    1494 |

> Lower is better

Measured in miliseconds(ms) using `time cat <filename>` on [10mb text file](./test/10mb.txt) 
consisting random latin character and numbers.
