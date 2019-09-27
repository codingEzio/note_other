### When in doubt, use *VM* or *Docker*.
- Don't use latest releases, use this ```node: 10.16.3```, ```npm: 6.9```
- Avoiding using sudo like ```sudo npm install -g```
    - do ```sudo chmod -R 775 /opt/WHERE_UR_NODE_AT``` first
    - if you still can't do it, config this before you use ```sudo```
        
        ```
        // my path would be /opt/node-v10.16.3-linux-x64/ELSE
        sudo ln -s /usr/local/bin/node /usr/bin/node
        sudo ln -s /usr/local/lib/node /usr/lib/node
        sudo ln -s /usr/local/bin/npm /usr/bin/npm
        ```