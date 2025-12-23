# ESPHome-Configs
Here are some of my personal ESPHome projects. I've coded some from scratch, but some configs I've gotten online and then refactored to my liking.

# How To Use
These files to not include the usual `logger:` and `api:` because my intended purpose for these is to be drop in. 
If you have an existing ESPHome working config, just drop these in under the board defininition and *remove any duplicates.* If you want to start fresh with this YAML, click Create Device in ESPHome, select the **New Device Setup** option, and select your board, and then paste one of these configs directly after the board definitions. (this usually keeps it nice and readable) This ensures that your encryption/api/logger/board is correct right away. Watch that indentation!!

# Think of an improvement? Please share!
Have an issue? Post an issue! I'd love to look into any issues and fix them.
Also, I am always adding new functions and making it even cleaner. If you improve my code in any ways, or implemement it into a cool project, please share *(if you'd like)*! PRs welcome. 
*(Note: I don't really care for a ton of lambda and complexity so if your improvement is adding a bunch of really complex lambdas and automations you might make your own repo for those :D)*
