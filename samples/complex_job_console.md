---
layout: samples
title: Scheduled Job
icon: fa-caret-right
group: complex
---

{{ page.title }}
===

### Steps


1. Create a project **job_console_project**
2. Then create a JavaScript service named **my_job_handler.js**
3. Within the service code, enter the following content:

#### Log Levels

```javascript

console.log("Hello from the My Job!");

```

4. Then create a **job** descriptor file **my_job.job**
5. Enter the following JSON content in it:

```json

{
	"expression":"0/10 * * * * ?",
	"handler":"job_console_project/my_job_handler.js",
	"description":"My Job"
}

```

6. Publish the project
8. After 10s in the *Console* view you should see the following lines:

	[2018-05-14T12:05:00.061Z] [INFO] Hello from the My Job!

---

For more information, see the *[API](../api/)* documentation.