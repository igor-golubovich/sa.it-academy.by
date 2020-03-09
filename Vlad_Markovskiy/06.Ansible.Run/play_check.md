# Terminal output from main playbook
```shell
anjey@anjey-UX31A:~/devops/06.Ansible$ ansible-playbook -i inventory.yaml play.yaml -e 'group=internal'

PLAY [internal] ****************************************************************

TASK [Gathering Facts] *********************************************************
Thursday 27 February 2020  17:23:19 +0300 (0:00:00.049)       0:00:00.049 ***** 
ok: [host1]
ok: [host2]

TASK [Print os and version] ****************************************************
Thursday 27 February 2020  17:23:22 +0300 (0:00:02.647)       0:00:02.697 ***** 
ok: [host1] => {
    "msg": " CentOS | 7.6 "
}
ok: [host2] => {
    "msg": " Ubuntu | 14.04 "
}

TASK [Print mount point] *******************************************************
Thursday 27 February 2020  17:23:22 +0300 (0:00:00.060)       0:00:02.758 ***** 
changed: [host2]
changed: [host1]

TASK [debug] *******************************************************************
Thursday 27 February 2020  17:23:23 +0300 (0:00:00.645)       0:00:03.403 ***** 
ok: [host1] => {
    "msg": [
        "Filesystem      Size  Used Avail Use% Mounted on",
        "/dev/sda1        40G  2.9G   38G   8% /",
        "devtmpfs        236M     0  236M   0% /dev",
        "tmpfs           244M     0  244M   0% /dev/shm",
        "tmpfs           244M  4.5M  240M   2% /run",
        "tmpfs           244M     0  244M   0% /sys/fs/cgroup",
        "tmpfs            49M     0   49M   0% /run/user/1001"
    ]
}
ok: [host2] => {
    "msg": [
        "Filesystem      Size  Used Avail Use% Mounted on",
        "udev            241M   12K  241M   1% /dev",
        "tmpfs            49M  364K   49M   1% /run",
        "/dev/sda1        40G  1.5G   37G   4% /",
        "none            4.0K     0  4.0K   0% /sys/fs/cgroup",
        "none            5.0M     0  5.0M   0% /run/lock",
        "none            245M     0  245M   0% /run/shm",
        "none            100M     0  100M   0% /run/user",
        "none            231G   32G  199G  14% /vagrant"
    ]
}

TASK [Print free mem] **********************************************************
Thursday 27 February 2020  17:23:23 +0300 (0:00:00.054)       0:00:03.458 ***** 
changed: [host2]
changed: [host1]

TASK [debug] *******************************************************************
Thursday 27 February 2020  17:23:23 +0300 (0:00:00.558)       0:00:04.017 ***** 
ok: [host1] => {
    "msg": [
        "              total        used        free      shared  buff/cache   available",
        "Mem:           487M         67M        301M        4.4M        118M        381M",
        "Swap:          2.0G          0B        2.0G"
    ]
}
ok: [host2] => {
    "msg": [
        "             total       used       free     shared    buffers     cached",
        "Mem:          489M       203M       286M       376K        11M        72M",
        "-/+ buffers/cache:       119M       370M",
        "Swap:           0B         0B         0B"
    ]
}

PLAY RECAP *********************************************************************
host1                      : ok=6    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
host2                      : ok=6    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   

Thursday 27 February 2020  17:23:23 +0300 (0:00:00.045)       0:00:04.062 ***** 
=============================================================================== 
Gathering Facts --------------------------------------------------------- 2.65s
Print mount point ------------------------------------------------------- 0.65s
Print free mem ---------------------------------------------------------- 0.56s
Print os and version ---------------------------------------------------- 0.06s
debug ------------------------------------------------------------------- 0.05s
debug ------------------------------------------------------------------- 0.05s
Playbook run took 0 days, 0 hours, 0 minutes, 4 seconds
```