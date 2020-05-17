# markdown

Deno Markdown module forked from https://github.com/ts-stack/markdown/tree/bb47aa8e625e89e6aa84f49a98536a3089dee831

### Example usage

Simple md2html.ts script:

```typescript
import { Marked } from "./mod.ts";

const decoder = new TextDecoder("utf-8");
const filename = Deno.args[0];
const markdown = decoder.decode(await Deno.readFile(filename));
const markup = Marked.parse(markdown);
console.log(markup);
```

Now running:

```bash
deno run --allow-read md2html.ts README.md > readme.html
```

Will output:

```html
<h1 id="markdown">markdown</h1>
<p>
  Deno Markdown module forked from
  <a
    href="https://github.com/ts-stack/markdown/tree/bb47aa8e625e89e6aa84f49a98536a3089dee831"
    >https://github.com/ts-stack/markdown/tree/bb47aa8e625e89e6aa84f49a98536a3089dee831</a
  >
</p>
<h3 id="example-usage">Example usage</h3>
<p>Simple md2html.ts script:</p>

<pre><code class="lang-typescript">import { Marked } from &quot;./mod.ts&quot;;

const decoder = new TextDecoder(&quot;utf-8&quot;);
const filename = Deno.args[0];
const markdown = decoder.decode(await Deno.readFile(filename));
const markup = Marked.parse(markdown);
console.log(markup);
</code></pre>
<p>
  Now running:
  <code>deno run --allow-read md2html.ts README.md &gt; readme.html</code>
  Will output:
</p>

<pre><code class="lang-html">
</code></pre>
```

---

### Notes

I had to do some changes to the source code to make the compiler happy, mostly fixes for things that were uninitialized and possibly null or undefined
