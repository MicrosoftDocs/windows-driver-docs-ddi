---
UID: NF:winsplp.SplPromptUIInUsersSession
title: SplPromptUIInUsersSession function
author: windows-driver-content
description: The SplPromptUIInUsersSession function displays a standard message box in the session indicated by the printer handle and job ID.
old-location: print\splpromptuiinuserssession.htm
old-project: print
ms.assetid: 5e458e3b-cfe2-4d48-b386-34d2a6c1d15e
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: SplPromptUIInUsersSession
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: The SplPromptUIInUsersSession function is available in Windows XP and later
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SplPromptUIInUsersSession
req.alt-loc: Spoolss.dll
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
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# SplPromptUIInUsersSession function



## -description
The <code>SplPromptUIInUsersSession</code> function displays a standard message box in the session indicated by the printer handle and job ID. 



## -syntax

````
BOOL SplPromptUIInUsersSession(
  _In_  HANDLE        hPrinter,
  _In_  DWORD         JobId,
  _In_  PSHOWUIPARAMS pUIParams,
  _Out_ DWORD         *pResponse
);
````


## -parameters

### -param hPrinter [in]

Handle to the printer.


### -param JobId [in]

Specifies the print job.


### -param pUIParams [in]

Pointer to a <a href="..\winsplp\ns-winsplp-showuiparams.md">SHOWUIPARAMS</a> structure that contains values that determine the appearance and behavior of the message box.


### -param pResponse [out]

Pointer to a memory location that contains either the user's response or the IDASYNC constant. For more information, see the Remarks section.


## -returns
On success, the <code>SplPromptUIInUsersSession</code> function returns <b>TRUE</b>; otherwise it returns <b>FALSE</b>.


## -remarks
If <i>pUIParams</i> -&gt;<b>bWait</b> is <b>FALSE</b>, this function returns immediately without waiting for the user's response. In that case, *<i>pResponse</i> is set to IDASYNC. 

If you plan to use this function in a driver intended to run under Windows 2000, you must load spoolss.dll by a call to the <b>LoadLibrary</b> function, and then find the address of this function within that DLL by a call to the <b>GetProcAddress</b> function. (<b>LoadLibrary</b> and <b>GetProcAddress</b> are described in the Microsoft Windows SDK documentation.) If the call to <b>GetProcAddress</b> fails, you must use an alternative mechanism to display user interface elements.


## -see-also
<dl>
<dt>
<a href="..\winsplp\ns-winsplp-showuiparams.md">SHOWUIPARAMS</a>
</dt>
<dt>
<a href="..\winsplp\nf-winsplp-splissessionzero.md">SplIsSessionZero</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20SplPromptUIInUsersSession function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

