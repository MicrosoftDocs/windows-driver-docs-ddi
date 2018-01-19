---
UID: NF:ntifs.SeUnregisterLogonSessionTerminatedRoutine
title: SeUnregisterLogonSessionTerminatedRoutine function
author: windows-driver-content
description: The SeUnregisterLogonSessionTerminatedRoutine routine unregisters a callback routine that was registered by an earlier call to SeRegisterLogonSessionTerminatedRoutine.
old-location: ifsk\seunregisterlogonsessionterminatedroutine.htm
old-project: ifsk
ms.assetid: 74f24296-cd42-402b-a61f-0199c4a07fd0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: SeUnregisterLogonSessionTerminatedRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SeUnregisterLogonSessionTerminatedRoutine
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: TOKEN_TYPE
---

# SeUnregisterLogonSessionTerminatedRoutine function



## -description
The <b>SeUnregisterLogonSessionTerminatedRoutine</b> routine unregisters a callback routine that was registered by an earlier call to <b>SeRegisterLogonSessionTerminatedRoutine</b>.



## -syntax

````
NTSTATUS SeUnregisterLogonSessionTerminatedRoutine(
  _In_ PSE_LOGON_SESSION_TERMINATED_ROUTINE CallbackRoutine
);
````


## -parameters

### -param CallbackRoutine [in]

Address of routine that was originally passed in to <b>SeRegisterLogonSessionTerminatedRoutine</b>.


## -returns
<b>SeUnregisterLogonSessionTerminatedRoutine</b> can return one of the following:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The callback routine was successfully removed.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The value of <i>CallbackRoutine</i> is <b>NULL</b>.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A list entry could not be found for the callback routine.

 


## -remarks
Each call to <b>SeRegisterLogonSessionTerminatedRoutine</b> must be matched by a subsequent call to <b>SeUnregisterLogonSessionTerminatedRoutine</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-semarklogonsessionforterminationnotification.md">SeMarkLogonSessionForTerminationNotification</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-seregisterlogonsessionterminatedroutine.md">SeRegisterLogonSessionTerminatedRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeUnregisterLogonSessionTerminatedRoutine routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

