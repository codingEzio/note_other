### Ah?
- 部分 binary 在安装时并无 “更改安装位置” 的选项。
- 此文件是为给出指导 于 一些更改起来不是那么容易的 binary (e.g. *Rust*)

### Section::Rust 
1. add this to your ```.bashrc``` (or ```.zshrc```)
    - ```export CARGO_HOME="ANY_LOCATION_IS_FINE"```<br>```export RUSTUP_HOME="ANY_LOCATION_IS_FINE"```
2. then install *Rust* (as usual)
    - e.g. ```curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain nightly```

### Section::Gradle 
1. Download the files 
    - link: [gradle.org/install](https://gradle.org/install/)
    - unzip
2. add this to your ```.bashrc``` (or ```.zshrc```)
    - ```export PATH=$PATH:FULL_PATH_OF_THAT_LOCATION/gradle-5.0/bin```
3. test it by ```gradle -v```

### Section::Go
1. Just **GIVE UP** 😕