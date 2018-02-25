---
UID: NF:ntifs.SeAppendPrivileges
title: SeAppendPrivileges function
author: windows-driver-content
description: The SeAppendPrivileges routine appends additional privileges to the privilege set in an access state structure.
old-location: ifsk\seappendprivileges.htm
old-project: ifsk
ms.assetid: b7a9142a-b6db-4a64-a5e3-d03d39ac3d09
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, P, S, SeAppendPrivileges, SeAppendPrivileges routine [Installable File System Drivers], d, e, g, i, ifsk.seappendprivileges, l, n, ntifs/SeAppendPrivileges, p, r, s, seref_c48fbff8-669f-4138-8f55-84bc083d9af5.xml, v"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	SeAppendPrivileges
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeAppendPrivileges function


## -description


The <b>SeAppendPrivileges</b> routine appends additional privileges to the privilege set in an access state structure.


## -syntax


````
NTSTATUS SeAppendPrivileges(
  _Inout_ PACCESS_STATE  AccessState,
  _In_    PPRIVILEGE_SET Privileges
);
````


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

<a href="..\wdm\ns-wdm-_privilege_set.md">PRIVILEGE_SET</a>



<a href="..\wdm\ns-wdm-_access_state.md">ACCESS_STATE</a>



<a href="..\ntifs\nf-ntifs-sefreeprivileges.md">SeFreePrivileges</a>



<a href="..\ntifs\nf-ntifs-sesetaccessstategenericmapping.md">SeSetAccessStateGenericMapping</a>



<a href="..\wdm\nf-wdm-seaccesscheck.md">SeAccessCheck</a>



<a href="..\ntifs\nf-ntifs-seprivilegecheck.md">SePrivilegeCheck</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeAppendPrivileges routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

