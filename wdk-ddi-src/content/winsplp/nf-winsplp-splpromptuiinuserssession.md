---
UID: NF:winsplp.SplPromptUIInUsersSession
title: SplPromptUIInUsersSession function (winsplp.h)
description: The SplPromptUIInUsersSession function displays a standard message box in the session indicated by the printer handle and job ID.
old-location: print\splpromptuiinuserssession.htm
tech.root: print
ms.assetid: 5e458e3b-cfe2-4d48-b386-34d2a6c1d15e
ms.date: 04/20/2018
ms.keywords: SplPromptUIInUsersSession, SplPromptUIInUsersSession function [Print Devices], print.splpromptuiinuserssession, spoolfnc_5b2379b2-c34b-4a98-b148-25a09f55be2b.xml, winsplp/SplPromptUIInUsersSession
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: The SplPromptUIInUsersSession function is available in Windows XP and later
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Spoolss.dll
api_name:
-	SplPromptUIInUsersSession
product:
- Windows
targetos: Windows
req.typenames: 
---

# SplPromptUIInUsersSession function


## -description


The <code>SplPromptUIInUsersSession</code> function displays a standard message box in the session indicated by the printer handle and job ID. 


## -parameters




### -param hPrinter [in]

Handle to the printer.


### -param JobId [in]

Specifies the print job.


### -param pUIParams [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562645">SHOWUIPARAMS</a> structure that contains values that determine the appearance and behavior of the message box.


### -param pResponse [out]

Pointer to a memory location that contains either the user's response or the IDASYNC constant. For more information, see the Remarks section.


## -returns



On success, the <code>SplPromptUIInUsersSession</code> function returns <b>TRUE</b>; otherwise it returns <b>FALSE</b>.




## -remarks



If <i>pUIParams</i> -&gt;<b>bWait</b> is <b>FALSE</b>, this function returns immediately without waiting for the user's response. In that case, *<i>pResponse</i> is set to IDASYNC. 

If you plan to use this function in a driver intended to run under Windows 2000, you must load spoolss.dll by a call to the <b>LoadLibrary</b> function, and then find the address of this function within that DLL by a call to the <b>GetProcAddress</b> function. (<b>LoadLibrary</b> and <b>GetProcAddress</b> are described in the Microsoft Windows SDK documentation.) If the call to <b>GetProcAddress</b> fails, you must use an alternative mechanism to display user interface elements.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562645">SHOWUIPARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562677">SplIsSessionZero</a>
 

 

