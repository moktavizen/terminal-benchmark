# Terminal Benchmark

Benchmarks of several Wayland terminal emulator. All test is done on newest
version (at the time of writing) with default config. Check respective terminal
directory for visualization.

These benchmarks is to help users in choosing terminal. Some may prioritize
rendering performance, others may prioritize memory usage and so on. These
benchmarks are not intended to pick on any specific terminal.

> Tested on older hardware, margin of results might be smaller in newer ones.

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

## Rendering

| run | alacritty | foot | ghostty |     kitty | wezterm |
|----:|----------:|-----:|--------:|----------:|--------:|
|   1 |       120 |  144 |     101 |       204 |      39 |
|   2 |       125 |  143 |     100 |       199 |      37 |
|   3 |       126 |  143 |     101 |       200 |      37 |
|   4 |       119 |  143 |      99 |       199 |      36 |
|   5 |       119 |  144 |     101 |       201 |      35 |
| avg |       122 |  143 |     100 | **_201_** |      37 |

> Higher is better

Measured in frames per second(FPS) using [DOOM-fire-zig](https://github.com/const-void/DOOM-fire-zig)
, sized at least 224w x 49h.

## Plaintext IO

| run | alacritty |      foot | ghostty | kitty | wezterm |
|----:|----------:|----------:|--------:|------:|--------:|
|   1 |       408 |       251 |     393 |   396 |    1248 |
|   2 |       393 |       263 |     420 |   418 |    1298 |
|   3 |       408 |       251 |     423 |   386 |    1157 |
|   4 |       389 |       249 |     409 |   398 |    1269 |
|   5 |       420 |       241 |     390 |   407 |    1258 |
| avg |       404 | **_251_** |     407 |   401 |    1246 |

> Lower is better

Measured in miliseconds(ms) using `time cat <filename>` on [11 MB Shakespeare's collection](./test/shakespeare.txt).

## VT IO Throughput

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

## Memory Usage

| run | alacritty |     foot | ghostty | kitty | wezterm |
|----:|----------:|---------:|--------:|------:|--------:|
|   1 |       132 |       45 |     256 |   143 |     200 |
|   2 |       100 |       44 |     165 |   127 |     118 |
|   3 |       104 |       31 |     166 |   103 |     116 |
|   4 |       119 |       37 |     164 |   111 |     127 |
|   5 |       106 |       31 |     175 |   105 |     134 |
| avg |       112 | **_38_** |     185 |   118 |     139 |

> Lower is better

Measured in megabytes(MB) using [btop](https://github.com/aristocratos/btop).
