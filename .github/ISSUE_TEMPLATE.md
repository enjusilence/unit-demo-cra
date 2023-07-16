---
title: Release {{ env.TAG }}
labels: RELEASE
---

**STATUS:** {{ env.STATUS }}
---
Workflow report can be seen here:
{{ env.WORKFLOW }}

**💡Author:** {{ env.AUTHOR }}
**📈Version:** {{ env.TAG }}
**📅Date:** {{ date | date('dddd, MMMM Do') }}

📃**Changelog:**
{{ env.CHANGELOG }}