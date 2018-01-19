---
UID: NF:winsplp.SplIsSessionZero
title: SplIsSessionZero function
author: windows-driver-content
description: The SplIsSessionZero function determines whether a certain print job (print handle plus job ID) was issued in session zero.
old-location: print\splissessionzero.htm
old-project: print
ms.assetid: 9d68a41d-0f2b-4cf0-92c6-8e05ce6b4378
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: SplIsSessionZero
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
req.alt-api: SplIsSessionZero
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

# SplIsSessionZero function



## -description
The <code>SplIsSessionZero</code> function determines whether a certain print job (print handle plus job ID) was issued in <a href="wdkgloss.s#wdkgloss.session_zero#wdkgloss.session_zero"><i>session zero</i></a>. 



## -syntax

````
DWORD SplIsSessionZero(
  _In_  HANDLE hPrinter,
  _In_  DWORD  JobID,
  _Out_ BOOL   *pIsSessionZero
);
````


## -parameters

### -param hPrinter [in]

Is a handle to the printer.


### -param JobID [in]

Specifies the print job.


### -param pIsSessionZero [out]

Pointer to a memory location that is set to <b>TRUE</b> if the SessionID for the session is zero; otherwise, this value is set to <b>FALSE</b>.


## -returns
On success, the <code>SplIsSessionZero</code> function returns ERROR_SUCCESS; otherwise this function returns a Win32 error code.


## -remarks
A driver that displays custom user interface elements can use the <code>SplIsSessionZero</code> function to determine whether the current job was issued in session 0. Such a driver can use this information to enable it to present user interface elements in the user's session, rather than in session zero. A related function, <a href="..\winsplp\nf-winsplp-splpromptuiinuserssession.md">SplPromptUIInUsersSession</a>, displays a standard Windows message box in the user's session. 

If you plan to use this function in a driver intended to run under Windows 2000, you must load spoolss.dll by a call to the <b>LoadLibrary</b> function, and then find the address of this function within that DLL by a call to the <b>GetProcAddress</b> function. (<b>LoadLibrary</b> and <b>GetProcAddress</b> are described in the Microsoft Windows SDK documentation.) If the call to <b>GetProcAddress</b> fails, you must use an alternative mechanism to display user interface elements.


## -see-also
<dl>
<dt>
<a href="..\winsplp\nf-winsplp-splpromptuiinuserssession.md">SplPromptUIInUsersSession</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20SplIsSessionZero function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

