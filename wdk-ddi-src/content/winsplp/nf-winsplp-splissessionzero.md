---
UID: NF:winsplp.SplIsSessionZero
title: SplIsSessionZero function (winsplp.h)
description: The SplIsSessionZero function determines whether a certain print job (print handle plus job ID) was issued in session zero.
tech.root: print
ms.date: 07/27/2022
keywords: ["SplIsSessionZero function"]
ms.keywords: SplIsSessionZero, SplIsSessionZero function [Print Devices], print.splissessionzero, spoolfnc_8fd112f0-f2bf-4a33-8411-c1ce7c620390.xml, winsplp/SplIsSessionZero
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SplIsSessionZero
 - winsplp/SplIsSessionZero
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Spoolss.dll
api_name:
 - SplIsSessionZero
---

## -description

The **SplIsSessionZero** function determines whether a certain print job (print handle plus job ID) was issued in [session zero](/windows-hardware/drivers/).

## -parameters

### -param hPrinter [in]

A handle to the printer.

### -param JobId

Specifies the print job.

### -param pIsSessionZero [out]

Pointer to a memory location that is set to **TRUE** if the SessionID for the session is zero; otherwise, this value is set to **FALSE**.

## -returns

On success, the **SplIsSessionZero** function returns ERROR_SUCCESS; otherwise this function returns a Win32 error code.

## -remarks

A driver that displays custom user interface elements can use the **SplIsSessionZero** function to determine whether the current job was issued in session 0. Such a driver can use this information to enable it to present user interface elements in the user's session, rather than in session zero. A related function, [SplPromptUIInUsersSession](./nf-winsplp-splpromptuiinuserssession.md), displays a standard Windows message box in the user's session.

If you plan to use this function in a driver intended to run under Windows 2000, you must load spoolss.dll by a call to the **LoadLibrary** function, and then find the address of this function within that DLL by a call to the **GetProcAddress** function. If the call to **GetProcAddress** fails, you must use an alternative mechanism to display user interface elements.

## -see-also

[SplPromptUIInUsersSession](./nf-winsplp-splpromptuiinuserssession.md)