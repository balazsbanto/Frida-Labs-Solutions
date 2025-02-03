# Frida-Labs-Solutions

My solutions for the [Frida-Labs challenges](https://github.com/DERE-ad2001/Frida-Labs) .

## Frida 0x1

```javascript
Java.perform(() => {
    const MainActivity = Java.use("com.ad2001.frida0x1.MainActivity");
    MainActivity.get_random.implementation = function() {
        const result = this.get_random();
        console.log("Result: " + result);
        return result;
    };
});
```

## Frida 0x2

```javascript
Java.perform(() => {
  const MainActivity = Java.use("com.ad2001.frida0x2.MainActivity");
  MainActivity.onCreate.implementation = function (savedInstanceState) {
    this.onCreate(savedInstanceState);
    MainActivity.get_flag(4919);
  };
});
```javascript
