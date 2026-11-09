<style>
  details {
    color: yellow;
  }

.shortcut {
  color: violet;
  font-size: 1.2em;
}

.center-bold {
  text-align: center;
  font-size: 1.2em;
  color: red;
}

h1 {
  color: green;
}

h2 {
  color: lightgreen;
}

h3 {
  color: orange;
}
</style>



<h1>Configure Users using GitBash Commands</h1>

- git config --global user.name "Benjamin Pedrin"
- git config --global user.email "pedrinb@students.westerntc.edu"
- git config --global core.autocrlf true
- git config --global --list

<h2>Creating SSH keys</h2>

- ssh-keygen -t ed25519 -C "pedrinb@students.westerntc.edu"

<h3>1. Start the agent and add the key (Holds key in memory while computer is on)</h3>

  - eval "$(ssh-agent -s)"
  - ssh-add ~/.ssh/id_ed25519

<h3>2. Print & Copy Public Key</h3>

- cat ~/.ssh/id_ed25519.pub

<h3>3. Testing your connection</h3>

- ssh -T git@github.com

<hr><hr>

<h1>Basic Switch and End Device Configuration</h1>

<h2>1. User EXEC Mode (View-Only)</h2>

- limited capabilities - cannot change config of device
- CLI prompt ends with ">"
- type "enable" to enter Privileged EXEC Mode from here

<h2>2. Privileged EXEC Mode</h2>

- Used to execute config commands
- CLI prompt ends with "#"
- type "configure terminal (<em class="shortcut">config t</em>)" to enter global config mode



<details>
<summary><strong>Show Image</strong></summary>

<img src="images/cli-modes.png" alt="Cisco CLI modes" width="750">
</details>


<h2>3. Global Config Mode</h2>

- Identified with prompt that ends with  "(config)#"
  - a. **<u>Line Configuration Mode</u>** - used to config console, SSH, Telnet or AUX access
  - b. **<u>Interface Configuration Mode</u>** - used to config a switch, port or router network interface

<br>

<details>
<summary><strong>Mode Changes</strong></summary>

<img src="images/mode-cmds.png" alt="Commands for Cisco CLI modes" width="750">
</details>
<br>

<h1>Syntax</h1>

<details>
<summary><strong>Syntax Help</strong></summary>

<img src="images/syntax-cheatsheet.png" alt="syntax cheatsheet" width="750">
</details>

For help in the CLI, enter a question mark (<em class="shortcut"> ? </em>)prompt.
- this is *context sensitive* meaning that the help you get will be determined by where and when you seek the help


<h1>Hotkeys & Shortcuts</h1>

<details>
<summary><strong>Hotkeys Cheatsheet</strong></summary>

<img src="images/hotkeys.png" alt="Hotkeys" width="750">
</details>

<br>

<h1>Naming Devices</h1>

- When naming a device, enter Privileged EXEC Mode on the device and use <strong><u>hostname</u></strong> or <strong><u>no hostname</u></strong> to change the name or return it to it's original prompt name

<br>

<h1>Configuring Passwords</h1>

<details>
<summary><strong>Password Commands</strong></summary>

<img src="images/passwordset.png" alt="Password creation commands" width="900">
</details>

<details>
<summary><strong>Encryption Commands</strong></summary>

<img src="images/encryptpass.png" alt="Password encryption commands" width="900">
</details>

<details>
<summary><strong>Banner Message</strong></summary>

<img src="images/bannermsg.png" alt="Banner message commands">
</details>

<br>

<div class="center-bold">Do Not Use "enable password" | Use "enable secret"</div>

<br>

Configurations commands "shortlist"
- show running-config
- show startup-config
- reload
- erase startup-config
- copy running-config startup-config (copy run start)

# Configuring A Virtual Interface
<details>
<summary><strong>Vlan Config</strong></summary>

<img src="images/vlanconfig.png" alt="Vlan Configuration">
</details>
command: "show ip interface brief"
<br>

<h1>Reference Models</h1>

<details>
<summary><strong>OSI Model</strong></summary>

<img src="images/osi-model.png" alt="OSI Reference Model">
</details>
<details>
<summary><strong>TCP/IP Model</strong></summary>

<img src="images/tcp-ip-model.png" alt="TCP/IP Reference Model">
</details>
<details>
<summary><strong>Model Comparison</strong></summary>

<img src="images/model-compare.png" alt="Model Comparison">
</details>
<br>