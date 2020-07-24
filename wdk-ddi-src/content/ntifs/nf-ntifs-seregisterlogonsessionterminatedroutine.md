---
UID: NF:ntifs.SeRegisterLogonSessionTerminatedRoutine
title: SeRegisterLogonSessionTerminatedRoutine function (ntifs.h)
description: The SeRegisterLogonSessionTerminatedRoutine routine registers a callback routine to be called when a logon session terminates. A logon session terminates when the last token referencing the logon session is deleted.
old-location: ifsk\seregisterlogonsessionterminatedroutine.htm
tech.root: ifsk
ms.assetid: 6cba6db5-b91f-46f0-939e-b02693c81438
ms.date: 04/16/2018
keywords: ["SeRegisterLogonSessionTerminatedRoutine function"]
ms.keywords: SeRegisterLogonSessionTerminatedRoutine, SeRegisterLogonSessionTerminatedRoutine routine [Installable File System Drivers], ifsk.seregisterlogonsessionterminatedroutine, ntifs/SeRegisterLogonSessionTerminatedRoutine, seref_7188551f-9c46-472f-8976-67ee53b994c5.xml
f1_keywords:
 - "ntifs/SeRegisterLogonSessionTerminatedRoutine"
 - "SeRegisterLogonSessionTerminatedRoutine"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeRegisterLogonSessionTerminatedRoutine
targetos: Windows
req.typenames: 
---

# SeRegisterLogonSessionTerminatedRoutine function


## -description


The <b>SeRegisterLogonSessionTerminatedRoutine</b> routine registers a callback routine to be called when a logon session terminates. A logon session terminates when the last token referencing the logon session is deleted.


## -parameters




### -param CallbackRoutine [in]

Address of routine to call when a logon session terminates.


## -returns



<b>SeRegisterLogonSessionTerminatedRoutine</b> can return one of the following:

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
The callback routine was successfully registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The value of <i>CallbackRoutine</i> is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A list entry could not be allocated for the callback routine.

</td>
</tr>
</table>
 




## -remarks



Each call to <b>SeRegisterLogonSessionTerminatedRoutine</b> must be matched by a subsequent call to <b>SeUnregisterLogonSessionTerminatedRoutine</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seunregisterlogonsessionterminatedroutine">SeUnregisterLogonSessionTerminatedRoutine</a>
 

 

