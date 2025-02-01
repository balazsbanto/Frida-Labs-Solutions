# Frida-Labs-Solutions

My solutions for the [Frida-Labs challenges](https://github.com/DERE-ad2001/Frida-Labs)

## Frida 0x1

```javascript
Java.perform(() => {
    const MainActivity = Java.use("com.ad2001.frida0x1.MainActivity");
    MainActivity.get_random.implementation = function() {
        console.log("get_random called");
        const result = this.get_random();
        console.log("Result: " + result);
        return result;
    };
});
```