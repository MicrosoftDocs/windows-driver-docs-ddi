---
UID: NF:ntifs.SeMarkLogonSessionForTerminationNotification
title: SeMarkLogonSessionForTerminationNotification function
author: windows-driver-content
description: The SeMarkLogonSessionForTerminationNotification routine marks a logon session so that the caller's registered callback routine is called when the logon session terminates.
old-location: ifsk\semarklogonsessionforterminationnotification.htm
tech.root: ifsk
ms.assetid: ca259e03-4770-48ce-a4c0-a26159a172aa
ms.date: 04/16/2018
ms.keywords: SeMarkLogonSessionForTerminationNotification, SeMarkLogonSessionForTerminationNotification routine [Installable File System Drivers], ifsk.semarklogonsessionforterminationnotification, ntifs/SeMarkLogonSessionForTerminationNotification, seref_417d6aa1-b506-463d-9506-3a3651873c4a.xml
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeMarkLogonSessionForTerminationNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeMarkLogonSessionForTerminationNotification function


## -description


The <b>SeMarkLogonSessionForTerminationNotification</b> routine marks a logon session so that the caller's registered callback routine is called when the logon session terminates. A logon session terminates when the last token referencing the logon session is deleted.


## -parameters




### -param LogonId [in]

Pointer to the logon ID of the logon session.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The logon session was successfully marked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The logon session was not found.

</td>
</tr>
</table>
 




## -remarks



To register the callback routine, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff556702">SeRegisterLogonSessionTerminatedRoutine</a>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556702">SeRegisterLogonSessionTerminatedRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556738">SeUnregisterLogonSessionTerminatedRoutine</a>
 

 

