---
UID: NF:ntifs.SeMarkLogonSessionForTerminationNotification
title: SeMarkLogonSessionForTerminationNotification function
author: windows-driver-content
description: The SeMarkLogonSessionForTerminationNotification routine marks a logon session so that the caller's registered callback routine is called when the logon session terminates.
old-location: ifsk\semarklogonsessionforterminationnotification.htm
old-project: ifsk
ms.assetid: ca259e03-4770-48ce-a4c0-a26159a172aa
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: SeMarkLogonSessionForTerminationNotification
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
req.alt-api: SeMarkLogonSessionForTerminationNotification
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

# SeMarkLogonSessionForTerminationNotification function



## -description
The <b>SeMarkLogonSessionForTerminationNotification</b> routine marks a logon session so that the caller's registered callback routine is called when the logon session terminates. A logon session terminates when the last token referencing the logon session is deleted.



## -syntax

````
NTSTATUS SeMarkLogonSessionForTerminationNotification(
  _In_ PLUID LogonId
);
````


## -parameters

### -param LogonId [in]

Pointer to the logon ID of the logon session.


## -returns
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The logon session was successfully marked.
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>The logon session was not found.

 


## -remarks
To register the callback routine, use <a href="..\ntifs\nf-ntifs-seregisterlogonsessionterminatedroutine.md">SeRegisterLogonSessionTerminatedRoutine</a>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.


## -see-also
<dl>
<dt>
<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-seregisterlogonsessionterminatedroutine.md">SeRegisterLogonSessionTerminatedRoutine</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-seunregisterlogonsessionterminatedroutine.md">SeUnregisterLogonSessionTerminatedRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeMarkLogonSessionForTerminationNotification routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

