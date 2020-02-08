### Note

- Wording
  - Most of this are based on _macOS_, I cannot guarantee this will work on all _Linux_ distributions.
  - Even if I mentioned _Linux_, it'll _probably_ & specfically work for _Ubuntu_.
- Install & Run
  1. For _Redis_, the setup is kinda easy <small>(`redis-server` & "_nothing_" [else](https://redis.io/documentation))</small>
  2. For _MongoDB_, it'll be a bit complicated.
- Compatibility
  - For _MongoDB_, you either use _latest_ **`4.2`** or the older **`4.0`** <small>(see [_here_](https://docs.mongodb.com/manual/installation/#supported-platforms))</small>.

### Issues

- You might encounter `SocketException: Address already in use` when running `mongod`
  1. find the port the previous `mongod` is using: `sudo lsof -iTCP -sTCP:LISTEN -n -P`
  2. kill that port: `kill PROCESS_ID`
  3. run: `mongod`

---

### The fastest way

##### Redis

- If you're using macOS, run `brew update && brew install redis`
- If you're using Linux, run `sudo apt-get install redis-server`

##### MongoDB

- If you're using macOS, run
  - [_Install_](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/#install-mongodb)
    1. `brew update && brew tap mongodb/brew`
    2. `brew install mongodb-community@4.2`
  - [_Run_](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/#run-mongodb)
    - run as a service: `brew services [start | stop] mongodb-community`
    - check if it's running: `ps aux | grep -v grep | grep mongod`
    - connect & use it: type `mongo` <small>(a cli for interacting)</small>
- If you're on Linux, run `sudo apt-get install redis-server`

---

### The manual way

##### Redis

- Download the binary
  - Visit [_official download website_](https://redis.io/download)
  - or `curl -O http://download.redis.io/redis-stable.tar.gz`
- `tar -xvzf` the `.tar.gz` file (if using _zsh_, simply type `extract THE_FILE`)

  - cd to the `src` directory

    |   Goal    | Command             | Note                                      |
    | :-------: | :------------------ | :---------------------------------------- |
    |  _Build_  | `make && make test` | the `make test` is optional               |
    | _Install_ | `make install`      | just remember restarting your terminal    |
    |  _Check_  | `redis-server`      | type `redis-cli ping` at another terminal |

##### MongoDB

- Download the binary
  - Visit [_official download website_](https://www.mongodb.com/download-center/community)
  - or `curl -O http://fastdl.mongodb.org/osx/mongodb-macos-x86_64-4.2.1.tgz/download`
- `tar -xvzf` the `.tar.gz` file (if using _zsh_, simply type `extract THE_FILE`)
  - either `cp` all the _binaries_ to the `/usr/local/bin/`
  - or create symbolic links to the binaries: `ln -s /YOUR_MONGO/bin/* /usr/local/bin/`
- more detailed & verbose way of running `mongod`: [here](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x-tarball/#run-mongodb)

---

### Reference

##### Redis

- [Introduction to Redis: Installation, CLI Commands, and Data Types](https://auth0.com/blog/introduction-to-redis-install-cli-commands-and-data-types/)
- [A extremely thorough intro on install Redis on Ubuntu](https://askubuntu.com/a/868862)

##### MongoDB

- Intro | Overview
  - [Get started with MongoDB in 10 minutes <small>(a short intro)</small>](https://www.freecodecamp.org/news/learn-mongodb-a4ce205e7739/)
  - [MongoDB and MySQL Compared <small>(more like an _overview_)</small>](https://www.mongodb.com/compare/mongodb-mysql)
- Reference
  - [MongoDB CRUD Operations](https://docs.mongodb.com/manual/crud/)
  - [`mongo` Shell Quick Reference](https://docs.mongodb.com/manual/reference/mongo-shell/)
  - [SQL to MongoDB Mapping Chart <small>(including _terms|concepts_, _cmd_, _cmd-inside_)</small>](https://docs.mongodb.com/manual/reference/sql-comparison/)
- Issues
  - [SocketException: Address already in use <small>(when running `mongod`)</small>](https://stackoverflow.com/a/50482140)
