# unpacker
A nodejs library to unpack p.a.c.k.e.d strings.

**Installation**

```
npm install unpacker
```


**Usage**
```
import { unpack, detect } from "unpacker";

detect(valueToTest); // Returns true/false if the input is packed string or not

unpack(valueToTest); // Returns the string in unpacked form
```

**Example 1 - Typescript**
```
import { unpack, detect } from "unpacker";

/*Since a packed string is hard to copy in the editor due to escape characters, here is the base64 version of it.*/
const packedString = 'ZXZhbChmdW5jdGlvbihwLGEsYyxrLGUsZCl7ZT1mdW5jdGlvbihjKXtyZXR1cm4gY307aWYoIScnLnJlcGxhY2UoL14vLFN0cmluZykpe3doaWxlKGMtLSl7ZFtjXT1rW2NdfHxjfWs9W2Z1bmN0aW9uKGUpe3JldHVybiBkW2VdfV07ZT1mdW5jdGlvbigpe3JldHVybidcXHcrJ307Yz0xfTt3aGlsZShjLS0pe2lmKGtbY10pe3A9cC5yZXBsYWNlKG5ldyBSZWdFeHAoJ1xcYicrZShjKSsnXFxiJywnZycpLGtbY10pfX1yZXR1cm4gcH0oJzYgNT0xOzQgMCgpezMuMihcJzBcJyl9Jyw3LDcsJ3Rlc3R8fGxvZ3xjb25zb2xlfGZ1bmN0aW9ufHRlc3REZWNsYXJhdGlvbnx2YXInLnNwbGl0KCd8JyksMCx7fSkp'

let valueToTest: string;

if (typeof atob === "undefined") {
  valueToTest = Buffer.from(packedString, "base64").toString("binary");  
} else {
  valueToTest = atob(packedString);
}

const result = unpack(valueToTest);

console.log(result);


```

**Example 2 - Plain javascript**
```
const unpacker = require("unpacker");

/*Since a packed string is hard to copy in the editor due to escape characters, here is the base64 version of it.*/
const packedString = 'ZXZhbChmdW5jdGlvbihwLGEsYyxrLGUsZCl7ZT1mdW5jdGlvbihjKXtyZXR1cm4gY307aWYoIScnLnJlcGxhY2UoL14vLFN0cmluZykpe3doaWxlKGMtLSl7ZFtjXT1rW2NdfHxjfWs9W2Z1bmN0aW9uKGUpe3JldHVybiBkW2VdfV07ZT1mdW5jdGlvbigpe3JldHVybidcXHcrJ307Yz0xfTt3aGlsZShjLS0pe2lmKGtbY10pe3A9cC5yZXBsYWNlKG5ldyBSZWdFeHAoJ1xcYicrZShjKSsnXFxiJywnZycpLGtbY10pfX1yZXR1cm4gcH0oJzYgNT0xOzQgMCgpezMuMihcJzBcJyl9Jyw3LDcsJ3Rlc3R8fGxvZ3xjb25zb2xlfGZ1bmN0aW9ufHRlc3REZWNsYXJhdGlvbnx2YXInLnNwbGl0KCd8JyksMCx7fSkp'

var valueToTest;

if (typeof atob === "undefined") {
  valueToTest = Buffer.from(packedString, "base64").toString("binary");  
} else {
  valueToTest = atob(packedString);
}

const result = unpacker.unpack(valueToTest);

console.log(result);
```