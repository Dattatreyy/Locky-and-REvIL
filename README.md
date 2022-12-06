# Locky-Ransomware
Checking tons of imports of unpacked Locky Ransomware

![1](https://user-images.githubusercontent.com/107531426/205825766-f115fc1b-ac6c-4d7c-8446-0a828a9201f9.PNG)
![2](https://user-images.githubusercontent.com/107531426/205825799-89fe2301-30bd-4afc-b038-0335cbbe2158.PNG)
![3](https://user-images.githubusercontent.com/107531426/205825835-8ed656c7-d1fd-46f4-8ead-8a946665735c.PNG)
![4](https://user-images.githubusercontent.com/107531426/205825855-861c9555-b34e-4c2d-ba43-64dd3320079b.PNG)
![5](https://user-images.githubusercontent.com/107531426/205825941-9d088bf2-05cb-4af7-831b-48d0461dc5ef.PNG)

SOME BREAKPOINTS TO CHECK OUT FOR GENERIC UNPACKING

CreateProcessInternalW  : Break on new Process created

VirtualProtect : Break on memory protection changed

ResumeThread : Break on thread resumed (possible injection)

VirtualAlloc : On return EAX has address of newly allocated memory segment. Follow in Dump to see if a PE is written to it.

HASH : bf7114f025fff7dbc6b7aff8e4edb0dd8a7b53c3766429a3c5f10142609968f9

![1](https://user-images.githubusercontent.com/107531426/205948045-d7ac7166-8a5b-4831-9161-582d133cd7a1.PNG)

![2](https://user-images.githubusercontent.com/107531426/205948074-d1ab46c3-8801-49d7-8daa-1d4871965d50.PNG)
