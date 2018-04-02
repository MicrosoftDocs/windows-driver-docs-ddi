---
UID: NF:ntifs.SeAppendPrivileges
title: SeAppendPrivileges function
author: windows-driver-content
description: The SeAppendPrivileges routine appends additional privileges to the privilege set in an access state structure.
old-location: ifsk\seappendprivileges.htm
old-project: ifsk
ms.assetid: b7a9142a-b6db-4a64-a5e3-d03d39ac3d09
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: SeAppendPrivileges, SeAppendPrivileges routine [Installable File System Drivers], ifsk.seappendprivileges, ntifs/SeAppendPrivileges, seref_c48fbff8-669f-4138-8f55-84bc083d9af5.xml
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
-	SeAppendPrivileges
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeAppendPrivileges function


## -description


The <b>SeAppendPrivileges</b> routine appends additional privileges to the privilege set in an access state structure.


## -parameters




### -param AccessState [in, out]

Pointer to a caller-allocated ACCESS_STATE structure representing the current access request. 


### -param Privileges [in]

Pointer to a caller-allocated PRIVILEGE_SET structure containing the privileges to be added. 


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
The append operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>SeAppendPrivileges</b> encountered a pool allocation failure when allocating memory for the new privileges.

</td>
</tr>
</table>
 




## -remarks



Initially, an access state structure can hold up to three privileges in its privilege set. If more than three privileges need to be stored, <b>SeAppendPrivileges</b> allocates a new privilege set from the paged pool and copies into it both the current privileges and the new privileges.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538840">ACCESS_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551860">PRIVILEGE_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563674">SeAccessCheck</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556656">SeFreePrivileges</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556686">SePrivilegeCheck</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556707">SeSetAccessStateGenericMapping</a>
 

 

