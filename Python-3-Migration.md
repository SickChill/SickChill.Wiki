So, there are some complications when upgrading to python3.

1. ### Bad Magic Number

   ```bash
   ImportError: bad magic number in...
   ```

   - ##### Nix based

     ```
     find /path/to/SickChill -name '*.pyc' -delete
     systemctl restart sickchill # or however you restart your service
     ```

   - ##### Windows
     _admin prompt_
     ```bash
     net stop sickchill
     cd C:\SickChill\SickChill
     del /S *.pyc
     net start sickchill
     ```
