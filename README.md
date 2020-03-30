# system-exec

This module is a promisified version of `child_process.exec` that allows you to access the text printed to the STDERR from 
the error object's message property.

## Example

```
const { exec } = require("system_exec");

async function main() {
    try {
        const result = await exec("ls");
        console.log(result);
    } catch (e) {
        console.log("Didn't work: " + e.message);
    }
}

main().catch(err => console.log(err.stack));
```