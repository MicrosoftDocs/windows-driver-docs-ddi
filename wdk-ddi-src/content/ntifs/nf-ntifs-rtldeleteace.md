---
UID: NF:ntifs.RtlDeleteAce
title: RtlDeleteAce function (ntifs.h)
description: The RtlDeleteAce routine deletes an access control entry (ACE) from a specified access control list (ACL).
old-location: ifsk\rtldeleteace.htm
tech.root: ifsk
ms.assetid: 2bf90d1d-887f-4d0c-8d79-e102a14dfe71
ms.date: 04/16/2018
ms.keywords: RtlDeleteAce, RtlDeleteAce routine [Installable File System Drivers], ifsk.rtldeleteace, ntifs/RtlDeleteAce, rtlref_68fe46f1-318a-48c6-9004-c338f52f41a5.xml
f1_keywords:
 - "ntifs/RtlDeleteAce"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows Server 2003 SP1 and later.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlDeleteAce
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlDeleteAce function


## -description


The <b>RtlDeleteAce</b> routine deletes an access control entry (ACE) from a specified access control list (ACL).


## -parameters




### -param Acl [in, out]

Pointer to the ACL to be modified. <b>RtlDeleteAce</b> deletes the specified ACE from this ACL. 


### -param AceIndex [in]

Specifies the ACE to delete. A value of zero corresponds to the first ACE in the ACL, 1 to the second ACE, and so on.


## -returns



<b>RtlDeleteAce</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameter values was invalid. Possible reasons include: 

<ul>
<li>
The specified ACL is invalid.

</li>
<li>
The specified index value is out of range. 

</li>
</ul>
STATUS_INVALID_PARAMETER is an error code. 

</td>
</tr>
</table>
 




## -remarks



For information about calculating the size of an ACL, see the Remarks section of the reference entry for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreateacl">RtlCreateAcl</a>. 

To add an ACE to an ACL, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtladdace">RtlAddAce</a>. 

To obtain a pointer to an ACE in an ACL, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlgetace">RtlGetAce</a>. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/ace">ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtladdace">RtlAddAce</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreateacl">RtlCreateAcl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlgetace">RtlGetAce</a>
 

 

