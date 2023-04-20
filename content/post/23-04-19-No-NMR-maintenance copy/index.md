---
title: Maintenance 
date: 2020-12-01
#image:
#  focal_point: 'top'
---

**No access** to the instrument next Tuesday (2023-04-25) because of maintenance 
<!--more-->
probably starting 10am till 5pm.

Today Bruker engineers will proceed with filling the Helium and boosting the field up to 600.14 MHz again.
After that, everything will be back to the situation from about 3 years ago, befor the first frequency adjustment became necessary.
Notice that experiments created between these two timespots will **not** work, since the detection frequency will be of.  I.e., should you want to create a new acquisition from an earlier dataset, e.g. through IconNMR's import tool, you first need to correct the base frequence :
```bash
edasp
default
save
````