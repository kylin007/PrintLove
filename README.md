# PrintLove
打印心型字符串



## 打印爱心结构字符串

* Python脚本
```
    print('\n'.join([''.join([('Str' [(x - y) % len('Str')]if ((x * 0.05) **2 + (y * 0.1) **2 - 1) **3 - (x * 0.05) **2 * (y * 0.1) **3 <= 0 else ' ') for x in range( - 30, 30)]) for y in range(30, -30, -1)]))
```



* 动态依次打印

```

public static void main(String[] args) {
        String key = "Str";// 想要打印的字符串
        final int[] index = {0};
        final StringBuffer[] str = {new StringBuffer()};
        IntStream.range(-20, 20).map(y -> -y).forEach(y -> IntStream.range(-30, 30).forEach(x -> {
            if(index[0] == key.length()){
                System.out.print(str[0].toString());
                str[0] = new StringBuffer();
                index[0] = 0;
                try {
                    Thread.sleep(RandomUtils.nextLong(50,100));
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
            boolean bl = Math.pow(Math.pow((x * 0.05), 2) + Math.pow((y * 0.1), 2) - 1, 3) - Math.pow(x * 0.05, 2) * Math.pow(y * 0.1, 3) <= 0;
            if (bl) {
                str[0].append(String.valueOf(key.charAt(index[0] % key.length())));
                index[0]++;
            } else {
                str[0].append(" ").append(x == 29 ? "\n" : "");
            }

        }));
        if(str[0].length()>0){
            System.out.print(str[0].toString());
        }

    }
```
