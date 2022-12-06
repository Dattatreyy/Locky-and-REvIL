# Locky-Ransomware
Checking tons of imports of unpacked Locky Ransomware

![1](https://user-images.githubusercontent.com/107531426/205825766-f115fc1b-ac6c-4d7c-8446-0a828a9201f9.PNG)
![2](https://user-images.githubusercontent.com/107531426/205825799-89fe2301-30bd-4afc-b038-0335cbbe2158.PNG)
![3](https://user-images.githubusercontent.com/107531426/205825835-8ed656c7-d1fd-46f4-8ead-8a946665735c.PNG)
![4](https://user-images.githubusercontent.com/107531426/205825855-861c9555-b34e-4c2d-ba43-64dd3320079b.PNG)
![5](https://user-images.githubusercontent.com/107531426/205825941-9d088bf2-05cb-4af7-831b-48d0461dc5ef.PNG)

SOME BREAKPOINTS TO CHECK OUT FOR GENERIC UNPACKING

CreateProcessInternalW  : BreakPoint if there is any new Process created

VirtualProtect : BreakPoint incase malware is trying to override the protected section (PE Section)

ResumeThread : Break on thread resumed (possible injection)

VirtualAlloc : On return EAX has address of newly allocated memory segment. Follow in Dump to see if a PE is written to it.

HASH : bf7114f025fff7dbc6b7aff8e4edb0dd8a7b53c3766429a3c5f10142609968f9

BP on the end of the VirtualAlloc. Because newly allocated Virtual Memory Address is returned in EAX. So everytime VitualAlloc will hit (ret) we have to look EAX which will have newly allocated memory address in it.

![1](https://user-images.githubusercontent.com/107531426/205948045-d7ac7166-8a5b-4831-9161-582d133cd7a1.PNG)

![2](https://user-images.githubusercontent.com/107531426/205948074-d1ab46c3-8801-49d7-8daa-1d4871965d50.PNG)

IAT

![1](https://user-images.githubusercontent.com/107531426/205992902-71c27e91-a2b3-4e2e-9d64-ff4c9ad1cc71.PNG)
![2](https://user-images.githubusercontent.com/107531426/205992944-3967b5ae-e323-489f-bfd7-e3a4a3ff35b5.PNG)
![3](https://user-images.githubusercontent.com/107531426/205992972-d0c39ada-4d61-4e6a-a734-c8df3c7c42ef.PNG)
![4](https://user-images.githubusercontent.com/107531426/205993018-a59788d7-d7ea-461e-963b-1ea69170d4aa.PNG)
![5 one step over and the debugger will laber the IAT](https://user-images.githubusercontent.com/107531426/205993095-3b44fbf8-118a-4e1b-9fca-b7e159fa4a65.PNG)
![6 Dump, IAT Autosearch and get imports and FIx dump](https://user-images.githubusercontent.com/107531426/205993120-d0e00ade-96c4-4487-b048-3f3fb63f66ec.PNG)
![7](https://user-images.githubusercontent.com/107531426/205993146-0960868b-029b-4110-81c6-1faac6aaee73.PNG)

