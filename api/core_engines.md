---
layout: api
title: Engines
icon: fa-check
---

{{ page.title }}
===

Engines object is used for executing a scripting service programmatically.

Version 4.x
---

- Module: **core/v4/engines**
- Alias: **core/engines**
- Definition: [https://github.com/eclipse/dirigible/issues/234](https://github.com/eclipse/dirigible/issues/234)
- Source: [/core/v4/engines.js](https://github.com/dirigiblelabs/api-core/blob/master/core/v4/engines.js)
- Facade: [ScriptEngineExecutorsManager](https://github.com/eclipse/dirigible/blob/4413511358a43a7c4b671a882e5e14f821d2704e/modules/engines/engine-api/src/main/java/org/eclipse/dirigible/engine/api/script/ScriptEngineExecutorsManager.java)
- Status: **stable**

### Basic Usage

```javascript
var engines = require("core/v4/engines");
var response = require("http/v4/response");

var result = engines.getEngine("javascript").execute("project1/hello", {});

response.println(result);
response.flush();
response.close();
```


### Definition

#### Functions

---

Function     | Description | Returns
------------ | ----------- | --------
**getEngine(type)**   | Returns the engine object per type provided | *Engine*
**getTypes()**   | Returns the list of the registered engine types | *array of strings*

### Objects

---

#### Engine

Function     | Description | Returns
------------ | ----------- | --------
**execute(module, context)**   | Executes a given module with a given context | *object*
**executeCode(source, context)**   | Executes a given source code with a given context | *object*


### Compatibility

Rhino | Nashorn | V8 | Graal |
----- | ------- | ---| ------|
 ✅   | ❌      | ❌  |  ✅   |

---

