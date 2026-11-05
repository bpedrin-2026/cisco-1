# Configuring User using GitBash
- git config --global user.name "Benjamin Pedrin"
- git config --global user.email "pedrinb@students.westerntc.edu"
- git config --global core.autocrlf true
- git config --global --list

## Creating SSH keys
- ssh-keygen -t ed25519 -C "pedrinb@students.westerntc.edu"

### 1. Start the agent and add the key (Holds key in memory while computer is on)

- eval "$(ssh-agent -s)"
- ssh-add ~/.ssh/id_ed25519

### 2. Print & Copy Public Key
- cat ~/.ssh/id_ed25519.pub

### 3. Testing your connection
- ssh -T git@github.com

<hr><hr>

# * ! * Basic Switch and End Device Configuration
### 1. User EXEC Mode (View-Only)
- limited capabilities - cannot change config of device
- CLI prompt ends with ">"
- type "enable" to enter Privileged EXEC Mode from here

### 2. Privileged EXEC Mode
- Used to execute config commands
- CLI prompt ends with "#"
- type "configure terminal (<em style="color: violet">config t</em>)" to enter global config mode



<details style="color: yellow">
<summary><strong>Show Image</strong></summary>

<img src="images/cli-modes.png" alt="Cisco CLI modes" width="750">
</details>



### 3. Global Config Mode
- Identified with prompt that ends with  "(config)#"
  - a. **<u>Line Configuration Mode</u>** - used to config console, SSH, Telnet or AUX access
  - b. **<u>Interface Configuration Mode</u>** - used to config a switch, port or router network interface

<br>

<details style="color: yellow">
<summary><strong>Mode Changes</strong></summary>

<img src="images/mode-cmds.png" alt="Commands for Cisco CLI modes" width="750">
</details>
<br>

# Syntax
<details style="color: yellow">
<summary><strong>Syntax Help</strong></summary>

<img src="images/syntax-cheatsheet.png" alt="syntax cheatsheet" width="750">
</details>

For help in the CLI, enter a question mark (<em style="color: violet">?</em>)prompt.
- this is *context sensitive* meaning that the help you get will be determined by where and when you seek the help


# Hotkeys & Shortcuts
<details style="color: yellow">
<summary><strong>Hotkeys</strong></summary>

<img src="images/hotkeys.png" alt="Hotkeys" width="750">
</details>

<br>

# Naming Devices
- When naming a device, enter Privileged EXEC Mode on the device and use <strong><u>hostname</u></strong> or <strong><u>no hostname</u></strong> to change the name or return it to it's original prompt name

<br>

# Configuring Passwords
<details style="color: yellow">
<summary><strong>Password Commands</strong></summary>

<img src="images/passwordset.png" alt="Password creation commands" width="900">
</details>

<details style="color: yellow">
<summary><strong>Encryption Commands</strong></summary>

<img src="images/encryptpass.png" alt="Password encryption commands" width="900">
</details>

<details style="color: yellow">
<summary><strong>Banner Message</strong></summary>

<img src="images/bannermsg.png" alt="Banner message commands">
</details>

<br>

**Be aware that "enable password" and "enable secret" are distinctly different**

<br>

Configurations commands "shortlist"
- show running-config
- show startup-config
- reload
- erase startup-config
- copy running-config startup-config (copy run start)

# Configuring A Virtual Interface
<details style="color: yellow">
<summary><strong>Vlan Config</strong></summary>

<img src="images/vlanconfig.png" alt="Vlan Configuration">
</details>
command: "show ip interface brief"
<br>