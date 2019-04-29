# Code Analysis Exercises

### 8.
**a)**

After each instruction:
```Assembly
MOV W0, 0x66666666
```

```
W0 = 0x66666666
```

---
```Assembly
MOV W1, 0xF000000F
```

```
W0 = 0x66666666
W1 = 0xF000000F
```
---
```Assembly
AND W0, W0, W1
```

```
W0 = 0x60000006
W1 = 0xF000000F
```
---
```Assembly
EOR W0, W0, W1
```

```
0x6 = 0b0110 | 0xF = 0b1111 | EOR(0b0110, 0b1111) = 0b1001 = 0x9
W0 = 0x90000009
W1 = 0xF000000F
```
---
```Assembly
ORR W0, W0, 0x66666666
```

```
0x9 = 0b1001 | 0x6 = 0b0110 | ORR(0b1001, 0b0110) = 0b1111 = 0xF
```

**Answer:** ```W0 = 0xF666666F```

**b)**

After each instruction:
```Assembly
MOV W0, 0x0000BEEF
```

```
W0 = 0x0000BEEF
```
---
```Assembly
ADDS W0, W0, 0x00008000
```

```
W0 = 0x00013EEF (flags are set, C = 1 since there was a carry)
```
---
```Assembly
MOV W1, 0x00003EEE
```

```
W0 = 0x00013EEF
W1 = 0x00003EEE
```
---
```Assembly
SBC W0, W0, W1
```

```
W0 = 0x00010001 (~C = 0)
```
---
```Assembly
ADC W0, W0, W0
```

**Answer:** ```W0 = 0x00020003```
