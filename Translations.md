**Currently the UI is in process of being fully translated.**  

##How does it work.?

The templates that we use for Sickrage contain the English texts. Those texts we have now "captured" by enclosing them in some code. This allows us to export the "texts" and store them in a *.POT file. From this *.POT file you can generate a language specific *.PO file, for translating.  
 
##Were do i start.?

There are 3 way's to translate.  

* With crowdin.com (web based tool)  
* With a program (like [PoEdit](https://poedit.net/) )  
* Directly edit the PO file on GitHub  

The easiest way is probably crowdin.com, so might be best suited for novice users.  
A program like PoEdit has been around a long time, and some users might prefer that over the web-based crowdin.com  
Directly edit the PO file with the GitHub editor is only advised for small and quick corrections.  


## Using crowdin.com  

Go to [crowdin.com](https://crowdin.com/project/sickrage) , click on the language you prefer and click on the sickrage.pot file. Now a new page is opened, where you can enter all translations.   

![pot](https://cloud.githubusercontent.com/assets/7928052/14351455/b78cee46-fccf-11e5-851e-b5846ab0a9d8.png)
![translating](https://cloud.githubusercontent.com/assets/7928052/14351456/b7ae6440-fccf-11e5-81a0-75014af30bbb.png)

## Using PoEdit  

First Download [PoEdit](https://poedit.net/) Then download the latest [Develop branch](https://github.com/SickRage/SickRage/archive/develop.zip) of sickrage and locate the SickRage/locale/sickrage.pot file.
If there isn't a *.po file for your language jet, than open the sickrage.pot file with PoEdit and it will generate one in your language. Now you can start translating the text to your language.
If there is already a *.po file for your language, than open the PO file with PoEdit and you can continue translating. However first go to `catalog` and `update from POT file`. This ensures that all the latest entries in the POT file are added to your PO file.  
Once you are done save the progress and PoEdit will create/update the PO file and create a*.MO file. This MO file is the actual translated file that Sickrage uses.  

![poedit](https://cloud.githubusercontent.com/assets/7928052/14350678/1546dce0-fccb-11e5-8067-78d9bc7fd215.png)
![pot update](https://cloud.githubusercontent.com/assets/7928052/14350679/1549b5f0-fccb-11e5-90b0-887d1a739585.png)


## Important things to consider while translating.

* If the original text is 20 characters than try to limit the translation to about the same number.  
  (A longer translation might not fit the field in the GUI.)  
* Dont do a simple 1:1 translation, try to describe the function properly.  
* Some text may include some code, make sure you use that also in the translation.!   
 
## Keeping the Pot file up-to-date

If you are maintaining the `pot` file or using our setup.py script to manage extracting messages from the source  or initializing/updating/compiling catalogs these are the available commands:  
(These require babel and mako modules)  

__To update the `pot` file__  
`python2 setup.py extract_messages`  

__To update all catalogs(*.po) with newly found msgstr__  
`python2 setup.py update_catalog`  

__To compile all catalogs(*.po) to *.mo__  
`python2 setup.py compile_catalog`  

__To initialize a new language that does not exist yet__  
`python2 setup.py init_catalog -l <lang_code>`  

