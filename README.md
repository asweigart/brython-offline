# brython-offline

Python interactive shell and file editor in a single .html file that works offline. Powered by [Brython](https://brython.info/index.html).

Open brython-3.14.3-offline.html in a web browser and enter Python instructions into the interactive shell.

## What is Brython?

Brython is an implementation of Python 3 that runs directly in a web browser.

Instead of writing JavaScript for browser behavior, you can write Python. Brython translates/executes that Python using JavaScript so it can interact with the page, DOM, events, and browser APIs.

Example:

```html
<script type="text/python">
from browser import document

def hello(event):
    document["output"].text = "Hello from Python"

document["button"].bind("click", hello)
</script>
```

It is mainly useful for browser scripting and educational projects. It is not CPython running in the browser, so compatibility with Python packages—especially packages with native extensions—is much more limited than with Pyodide.

## What's the difference between Brython and Pyodide?

| | Brython | Pyodide |
|---|---|---|
| Core approach | Implements Python in JavaScript | Compiles CPython to WebAssembly |
| Compatibility | Python-like, but not full CPython compatibility | Very close to normal CPython |
| Python packages | Limited; many CPython packages won't work | Supports many packages, including NumPy, pandas, SciPy, etc. |
| Browser/DOM integration | Very direct and convenient | Available, but somewhat more explicit |
| Startup/download size | Usually smaller/lighter | Larger runtime |
| Performance | Good for browser scripting | Better suited to computational Python |
| Native extensions | Generally unsupported | Many packages are precompiled to WebAssembly |
| Best use | Replacing JavaScript with Python for frontend logic | Running real Python/data-science code in the browser |