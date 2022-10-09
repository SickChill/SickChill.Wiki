**Currently the UI is in process of being fully translated.**

## How does it work.?

The templates that we use for SickChill contain the English texts. Those texts we have now `captured` by enclosing them in some code. This allows us to export the `texts` and store them in a `POT` file. From this `POT` file you can generate a language specific `PO` file, for translating.

## Using crowdin.com

Go to [crowdin.com](https://crowdin.com/project/sickchill) , and login with your account.
click on the language you prefer and click on the `messages.pot` file. Now a new page is opened, where you can enter all translations.

![pot](https://cloud.githubusercontent.com/assets/7928052/14351455/b78cee46-fccf-11e5-851e-b5846ab0a9d8.png)
![translating](https://cloud.githubusercontent.com/assets/7928052/14351456/b7ae6440-fccf-11e5-81a0-75014af30bbb.png)

## Important things to consider while translating.

- If the original text is 20 characters than try to limit the translation to about the same number.  
  (A longer translation might not fit the field in the GUI.)
- Don't do a simple 1:1 translation, try to describe the function properly.
- Some text may include some code, make sure you use that also in the translation.!

## Keeping the Pot file up-to-date

If you are maintaining the `pot` file or using our setup.py script to manage extracting messages from the source or initializing/updating/compiling catalogs these are the available commands:  
(These require babel and mako modules)

**To update the `pot` file**  
`python2 setup.py extract_messages`

**To update all catalogs(\*.po) with newly found msgstr**  
`python2 setup.py update_catalog`

**To compile all catalogs(_.po) to _.mo**  
`python2 setup.py compile_catalog`

**To initialize a new language that does not exist yet**  
`python2 setup.py init_catalog -l <lang_code>`
