### **Convert the Project to CommonJS**
![[Pasted image 20250313150208.png]]

If you want to continue using `require` instead of `import`:

1. Remove the `"type": "module"` line from your `package.json`.
    
2. Your project will now be treated as a **CommonJS** module by default.
    
3. Keep your code as it is:

```js
const qr = require('qr-image');
const fs = require('fs');

const qr_svg = qr.image('I love QR!', { type: 'svg' });
qr_svg.pipe(fs.createWriteStream('i_love_qr.svg'));

const svg_string = qr.imageSync('I love QR!', { type: 'svg' });
console.log(svg_string);


```

4. Run the script:
    `node index.js`