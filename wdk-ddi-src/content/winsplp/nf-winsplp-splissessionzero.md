---
UID: NF:winsplp.SplIsSessionZero
title: SplIsSessionZero function
author: windows-driver-content
description: The SplIsSessionZero function determines whether a certain print job (print handle plus job ID) was issued in session zero.
old-location: print\splissessionzero.htm
tech.root: print
ms.assetid: 9d68a41d-0f2b-4cf0-92c6-8e05ce6b4378
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: SplIsSessionZero, SplIsSessionZero function [Print Devices], print.splissessionzero, spoolfnc_8fd112f0-f2bf-4a33-8411-c1ce7c620390.xml, winsplp/SplIsSessionZero
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: This function is available in Windows XP and later.
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
-	SplIsSessionZero
product:
- Windows
targetos: Windows
req.typenames: 
---

# SplIsSessionZero function


## -description


The <code>SplIsSessionZero</code> function determines whether a certain print job (print handle plus job ID) was issued in <a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">session zero</a>. 


## -parameters




### -param hPrinter [in]

Is a handle to the printer.


### -param JobId




### -param pIsSessionZero [out]

Pointer to a memory location that is set to <b>TRUE</b> if the SessionID for the session is zero; otherwise, this value is set to <b>FALSE</b>.


#### - JobID [in]

Specifies the print job.


## -returns



On success, the <code>SplIsSessionZero</code> function returns ERROR_SUCCESS; otherwise this function returns a Win32 error code.




## -remarks



A driver that displays custom user interface elements can use the <code>SplIsSessionZero</code> function to determine whether the current job was issued in session 0. Such a driver can use this information to enable it to present user interface elements in the user's session, rather than in session zero. A related function, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562679">SplPromptUIInUsersSession</a>, displays a standard Windows message box in the user's session. 

If you plan to use this function in a driver intended to run under Windows 2000, you must load spoolss.dll by a call to the <b>LoadLibrary</b> function, and then find the address of this function within that DLL by a call to the <b>GetProcAddress</b> function. (<b>LoadLibrary</b> and <b>GetProcAddress</b> are described in the Microsoft Windows SDK documentation.) If the call to <b>GetProcAddress</b> fails, you must use an alternative mechanism to display user interface elements.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562679">SplPromptUIInUsersSession</a>
 

 

