So, there are some complications when upgrading to python3.

### Bad Magic Number

```bash
ImportError: bad magic number in...
```

- ##### Nix (Linux/Unix) based

  ```
  find /path/to/SickChill -name '*.pyc' -delete
  systemctl restart sickchill # or however you restart your service
  ```

- ##### Windows

  _run command prompt as an administrator_

  (Click on Start button -> type "cmd" -> right-click on "Command Prompt" -> click "Run as administrator")

  At the command prompt:

  ```bash
  net stop sickchill
  cd C:\SickChill\SickChill
  del /S *.pyc
  net start sickchill
  ```
