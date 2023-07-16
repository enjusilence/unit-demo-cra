---
title: RELEASE {{ env.TAG }}
labels: RELEASE
---

STATUS: {{ env.STATUS }}
Workflow report can be seen here: {{ env.WORKFLOW }}

Author: {{ env.AUTHOR }}
Date: {{ date | date('dddd, MMMM Do') }}
Changelog:
{{ env.CHANGELOG }}