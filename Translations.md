The UI is in process of being fully translated.  

We are in the process of adding [Crowdin](https://crowdin.com/) integration to make it easier for translators to contribute, and for us to make sure the `pot` and `*.po` are always up to date.  

In the mean time, is a `pot` file at `locale/messages.pot`, which can be used with [Poedit](https://poedit.net/)  

If you are maintaining the `pot` file or using our setup.py script to manage extracting messages from the source  or intializing/updating/compiling catalogs these are the available commands:  
(These require babel and mako modules)  

__To update the `pot` file__  
`python2 setup.py extract_messages`  

__To update all catalogs(*.po) with newly found msgstr__  
`python2 setup.py update_catalog`  

__To compile all catalogs(*.po) to *.mo__  
`python2 setup.py compile_catalog`  

__To initialize a new language that does not exist yet__  
`python2 setup.py init_catalog -l <lang_code>`  