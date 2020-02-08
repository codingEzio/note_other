### Note

- Different _MySQL_ versions: _`5.7`_ and _`8.0`_ <small>(adopation rate: _35%_, _17%_)</small>
  - I just made a quick search on [_most used version_](https://www.google.com/search?q=mysql+most+used+version), these are the mostly used.
- GUI software <small>(most I've mentioned is cross-platform app)</small>
  - [_pgAdmin_](https://www.pgadmin.org/download/)
  - [_Sequel Pro_](https://sequelpro.com/download): macOS only.
  - [_MySQL Workbench_](https://dev.mysql.com/downloads/workbench/): **not recommended** for _macOS_ `10.13.*` users.
  - [_Navicat Prenium_](https://www.navicat.com/en/store/navicat-premium-plan): not free, other than that, you can manage almost all DBs in this software.
- Both of these two DBMSes are easy to install via _package managers_
  - it might be a bit complicated if you wanna install it on _macOS_ using a _tarball_
- Data loss
  - After uninstalled *PostgreSQL*, all of your data/users will be ***LOST**.

### Issues

- Do not use _MySQL Workbench_.
- The data/log of different versions of *PostgreSQL* might be **imcompatible**!
  1. Install: `brew install postgresql@VERSION`
  2. Servies: `brew services start postgresql@VERSION`

---

### The fastest way

##### MySQL

- If you're using macOS <small>(using `brew`)</small>
  1. `brew update && brew install mysql@8.0`
  2. `brew services start mysql`
  3. `mysql_secure_installation` <small>(tiny customization & setting up DB's `root` password)</small>
- If you're using Linux, see _references_ at the bottom.

##### PostgreSQL

- If you're on macOS, run `brew update && brew install postgresql@12` <small>(see [_more_](https://www.postgresql.org/download/macosx/))</small>
- If you're on Linux, run `sudo apt-get install postgresql-11` <small>(see [_more_](https://www.postgresql.org/download/linux/ubuntu/))</small>

---

### The manual way

##### MySQL

- Installing via `.dmg` file <small>(**macOS** only)</small>
  - Download [_here_](https://dev.mysql.com/downloads/mysql/)
  - Follow [_this tutorial_](https://dev.mysql.com/doc/mysql-osx-excerpt/5.7/en/osx-installation-pkg.html) to finish the installation
- I havn't try the _tarball_'s way, see this if you do wanna try it
  - [_Installing MySQL on Unix/Linux Using Generic Binaries_](https://dev.mysql.com/doc/refman/5.7/en/binary-installation.html)

##### PostgreSQL

- Installing via files like `.dmg`, `.run` and `.exe` <small>([about `.run` file](https://askubuntu.com/questions/13415/what-are-run-files))</small>

  - Download [_here_](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads)
  - _Click_ and _Click_.

- Installing via tarball <small>(these steps were based on version `12.1`)</small>

  - Download [_here_](https://www.postgresql.org/ftp/source/v12.1/)
  - `tar -xvzf postgresql-12.1.tar.gz && cd postgresql-12.1`
  - then you can
    1. **Either** go see the [online documentation](https://www.postgresql.org/docs/12/install-short.html) or the offiline `INSTALL` file <small>(same content)</small>,
    2. **or** go directly see the _shorter version_: [here](https://www.postgresql.org/docs/12/install-short.html)

- Installing via `.zip` <small>(not recommended but _okay_)</small>
  - Download [_here_](https://www.enterprisedb.com/download-postgresql-binaries)
  - `unzip` it <small>(it might take a _looooooong_ time)</small> <small>(size: `~5.5GiB`)</small>
    - It also includes _pgAdmin_ by default while itself account for approximately `4.2GiB`
    - It has _everything_ <small>(the GUI's way might have as well:))</small>

---

### Reference

##### MySQL

- [How to use MySQL on macOS <small>(including installation & configuration, quite nice)</small>](https://www.dev2qa.com/how-to-use-mysql-on-mac/)
- [How To Install the Latest MySQL on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-the-latest-mysql-on-ubuntu-16-04)
- [Install MySQL Server on Ubuntu <small>(MySQL Server kinda == MySQL)</small>](https://support.rackspace.com/how-to/installing-mysql-server-on-ubuntu/)

##### PostgreSQL

- [How To Install and Use PostgreSQL on Ubuntu 18.04 <small>(do see the _configuration_ part)</small>](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-18-04)
- [Installing Postgres via `brew` <small>(including _setup_ & _common-used commands_)</small>](https://gist.github.com/ibraheem4/ce5ccd3e4d7a65589ce84f2a3b7c23a3)
