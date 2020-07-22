<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [puppeteer](./puppeteer.md) &gt; [Frame](./puppeteer.frame.md) &gt; [$eval](./puppeteer.frame._eval.md)

## Frame.$eval() method

<b>Signature:</b>

```typescript
$eval<ReturnType>(selector: string, pageFunction: (element: Element, ...args: unknown[]) => ReturnType | Promise<ReturnType>, ...args: SerializableOrJSHandle[]): Promise<WrapElementHandle<ReturnType>>;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  selector | string | the selector to query for |
|  pageFunction | (element: Element, ...args: unknown\[\]) =&gt; ReturnType \| Promise&lt;ReturnType&gt; | the function to be evaluated in the frame's context |
|  args | [SerializableOrJSHandle](./puppeteer.serializableorjshandle.md)<!-- -->\[\] | additional arguments to pass to <code>pageFuncton</code> |

<b>Returns:</b>

Promise&lt;[WrapElementHandle](./puppeteer.wrapelementhandle.md)<!-- -->&lt;ReturnType&gt;&gt;

## Remarks

This method runs `document.querySelector` within the frame and passes it as the first argument to `pageFunction`<!-- -->.

If `pageFunction` returns a Promise, then `frame.$eval` would wait for the promise to resolve and return its value.

## Example


```js
const searchValue = await frame.$eval('#search', el => el.value);

```
