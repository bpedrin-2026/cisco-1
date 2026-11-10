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
  color: white;
  text-decoration: underline;
}

.underline-points {
  color: white;
  text-decoration: underline;
  font-size: 1.2em;
}

.normal {
  color: white;
}

.HOT {
  color: red;
  font-weight: 1.2em;
}

.footnote {
  font-style: italic;
  color: violet;
}

</style>



<h1>Configure Users using GitBash Commands</h1>

<details>
<summary>Commands</summary>

- git config --global user.name "Benjamin Pedrin"
- git config --global user.email "pedrinb@students.westerntc.edu"
- git config --global core.autocrlf true
- git config --global --list
</details>

<h1>Creating SSH keys</h1>

<details>
<summary>Commands</summary><br>

<span class="normal">

- ssh-keygen -t ed25519 -C "pedrinb@students.westerntc.edu"


<ol>
  <li><span class="underline-points">Start the agent and add the key</span>
    <ul>
      <li>(Holds key in memory while computer is on)</li>
      <li>eval "$(ssh-agent -s)"</li>
      <li>ssh-add ~/.ssh/id_ed25519</li>
    </ul>
  </li>

</span>

<h3>2. Print & Copy Public Key</h3>

- cat ~/.ssh/id_ed25519.pub

<h3>3. Testing your connection</h3>

- ssh -T git@github.com
</details>

<hr><hr>

<h1>Basic Switch and End Device Configuration</h1>

<details>
<summary>Access Methods</summary>
<h3>Access Methods</h3>

<ul class="normal">
  <li>Console
    <ul>
      <li>Physical management port</li>
      <li>Out-of-Band - refers to access via a cable or dedicated management channel used for maintenance only!</li>
      <li>Cable required</li>
    </ul>
  </li>
  <li>Telnet
    <ul>
      <li>In-Band - <span class="HOT">Insecure</span></li>
      <li>Over Network - used once the IP has been configured</li>
      <li>Requires active networking services on the device</li>
      <li class="HOT">NOT ENCRYPTED</li>
    </ul>
  </li>
  <li>Secure Shell (SSH)
    <ul>
      <li>In-Band</li>
      <li class="HOT">SECURE</li>
    </ul>
  </li>
</ul>

<h2>1. User EXEC Mode Commands(View-Only)</h2>

<h2>2. Privileged EXEC Mode Commands</h2>

<h2>3. Global Config Mode</h2>

- Identified with prompt that ends with  "(config)#"
  - a. **<u>Line Configuration Mode</u>** - used to config console, SSH, Telnet or AUX access
  - b. **<u>Interface Configuration Mode</u>** - used to config a switch, port or router network interface

</details>
<br>

<details>
<summary><strong>Mode Changes</strong></summary>

<img src="images/mode-cmds.png" alt="Commands for Cisco CLI modes" width="750">
</details>
<br>


<h1>Commands</h1>

- line interface vlan 1
- no ip domain-lookup


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

<h3>Setting Passwords</h3>

<span class="normal">
  <ul>
    <li>console password
      <ul>
        <li>line console 0</li>
        <li>password xT6yR</li>
        <li>login</li>
        <li>end (exit can be used to exit line mode)</li>
      </ul>
    </li>
<br>
    <li>enable password
      <ul>
        <li>config t - (enter configuration mode)</li>
        <li>enable password R7gS0e</li>
        <li>exit - (when ready to exit config mode)</li>
      </ul>
    </li>
<br>
    <li>enable secret
      <ul>
        <li>config t - (enter configuration mode)</li>
        <li>enable secret sEd9o7</li>
        <li>exit - (when ready to exit config mode)</li>
      </ul>
    </li>
<br>
    <li>vty password (Virtual Teletype)

  <span class="footnote">Virtual terminal that provides remote access for Telnet and SSH sessions</span>
      <ul>
        <li>line vty 0 15</li>
        <li>password x8Hc5ja</li>
        <li>login</li>
        <li>end (to return to enable mode); exit (to return to config mode)</li>
      </ul>
  <span class="footnote">To configure different security options for different virtual lines
      <ul>
        <li>line vty 0 4</li>
        <li>password MyPass</li>
        <li>login local</li>
        <li>transport input ssh</li>
        <li>access-class 101 in</li>
      </ul>
<br>
      <ul>
        <li>line vty 5 15</li>
        <li>password MyPass</li>
        <li>login local</li>
        <li>transport input ssh telnet</li>
        <li>access-class 102 in</li>
      </ul>
    </li>
</span>
    <li>username/password authentication
      <ul>
        <li>Router(config)# username admin secret MyStrongPassword</li>
        <li>Router(config)# line console 0</li>
        <li>Router(config-line)# login local</li>
      </ul>
    </li>
  </ul>

  <span class="HOT">To clear a password, simply type "NO" before any command</span>
</span>

</details>

<details>
  <summary><strong>Encryption Commands</strong></summary>
  <h3>Encryption</h3>

  <ul class="normal">
    <li>service password-encryption
  </ul>

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

"All People Seem To Need Data Processing"

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