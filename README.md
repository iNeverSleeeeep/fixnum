# fixnum
```c
作者：韦易笑
链接：https://zhuanlan.zhihu.com/p/149517485
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

#define cfixed_from_int(i)      (((cfixed)(i)) << 16)
#define cfixed_from_float(x)    ((cfixed)((x) * 65536.0f))
#define cfixed_from_double(d)   ((cfixed)((d) * 65536.0))
#define cfixed_to_int(f)        ((f) >> 16)
#define cfixed_to_float(x)      ((float)((x) / 65536.0f))
#define cfixed_to_double(f)     ((double)((f) / 65536.0))
#define cfixed_const_1          (cfixed_from_int(1))
#define cfixed_const_half       (cfixed_const_1 >> 1)
#define cfixed_const_e          ((cfixed)(1))
#define cfixed_const_1_m_e      (cfixed_const_1 - cfixed_const_e)
#define cfixed_frac(f)          ((f) & cfixed_const_1_m_e)
#define cfixed_floor(f)         ((f) & (~cfixed_const_1_m_e))
#define cfixed_ceil(f)          (cfixed_floor((f) + 0xffff))
#define cfixed_mul(x, y)        ((cfixed)((((int64_t)(x)) * (y)) >> 16))
#define cfixed_div(x, y)        ((cfixed)((((int64_t)(x)) << 16) / (y)))
#define cfixed_const_max        ((int64_t)0x7fffffff)
#define cfixed_const_min        (-((((int64_t)1) << 31)))
typedef int32_t cfixed;
```
