# Virtru Zendesk App

All the code is located in assets/iframe.html. It's slightly messy, I tried to add comment to clarify what is happening. 

Right now the app type is ticket_editor which means its in the toolbar under the comment editor. You can also position it in other places which might be better if you want to add more buttons and options etc.
(locations: https://developer.zendesk.com/api-reference/apps/apps-support-api/introduction/)

Issues with current version:
- it occasionally does not work with pictures (and im guess other non text files), im able to upload, attach, and decrypt but when i try to open the decrypted file it says it can't open or that the file type does not match. its a known issue that zendesk api does not do well with binary file uploads (see this thread: https://support.zendesk.com/hc/en-us/articles/223137947/comments/360005290474) but im not sure if the corruption is happening with the zendesk upload, or how im converting it to a file object after encryption, etc. i would assume its something wrong with the actual base file since im able to decrypt successfully thus the manifest probably has not been mangled. more testing probably needed here
- it currently is not able to upload multiple files at once - that should be simple to fix, just using a list and looping over to upload multiple files then attaching them with a list of the tokens.