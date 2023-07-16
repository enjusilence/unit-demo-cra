---
title: RELEASE {{ env.TAG }}
labels: RELEASE
---

STATUS: {{ env.STATUS }}
<!-- Check workflow: {{ env.WORKFLOW }} -->

Author: {{ env.AUTHOR }}
Date: {{ date | date('dddd, MMMM Do') }}
Changelog:
{{ env.CHANGELOG }}