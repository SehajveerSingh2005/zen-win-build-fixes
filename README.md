\# Possible reasons and fixes for issues when trying to build zen (cuz windows suck)



\## 1. `npm run import` failing

if imports are failing even after `npm run reset-ff`, the reason could be that the patches had Windows-style \\r\\n line endings, but git apply requires Unix-style \\n. The \\r characters corrupted the patch parser at line boundaries.



To fix this, just convert them from CRLF to LF.



\## 2. `error: EPERM: operation not permitted, rename '.surfer/engine/ff' -> '/engine'`

> The root cause for this is still not clear.



For me, what fixed this was making sure .surfer and engine are deleted and not in lock before you do npm run init or surfer download again. Also try switching IDEs or using just the terminal (yeah i know weird but it worked for me)

