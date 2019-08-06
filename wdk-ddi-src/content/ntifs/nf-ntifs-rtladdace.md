---
UID: NF:ntifs.RtlAddAce
title: RtlAddAce function (ntifs.h)
description: The RtlAddAce routine adds one or more access control entries (ACEs) to a specified access control list (ACL).
old-location: ifsk\rtladdace.htm
tech.root: ifsk
ms.assetid: 291b1fa9-5f42-49b6-b6de-20054a832bb2
ms.date: 04/16/2018
ms.keywords: RtlAddAce, RtlAddAce routine [Installable File System Drivers], ifsk.rtladdace, ntifs/RtlAddAce, rtlref_798d31d8-c233-4154-981d-a84cfdd95045.xml
ms.topic: function
f1_keywords:
 - "ntifs/RtlAddAce"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Server 2003 with SP1.
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlAddAce
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlAddAce function


## -description


The <b>RtlAddAce</b> routine adds one or more access control entries (ACEs) to a specified access control list (ACL).


## -parameters




### -param Acl [in, out]

Pointer to the ACL to be modified. <b>RtlAddAce</b> adds the specified ACEs to this ACL. 


### -param AceRevision [in]

ACL revision level of the ACE to be added. Windows version requirments are the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>ACL_REVISION</dt>
</dl>
</td>
<td width="60%">
The revision level valid on all Windows versions.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>ACL_REVISION_DS</dt>
</dl>
</td>
<td width="60%">
The revision level valid starting with Windows 2000.

<div class="alert"><b>Note</b>  <i>AceRevision</i> must be ACL_REVISION_DS if the ACL in <i>Acl</i> contains an object-specific ACE.</div>
<div> </div>
</td>
</tr>
</table>
 


### -param StartingAceIndex [in]

Specifies the position in the ACL's list of ACEs at which to add new ACEs. A value of zero inserts the ACEs at the beginning of the list. A value of MAXULONG appends the ACEs to the end of the list.


### -param AceList [in]

Pointer to a buffer containing a list of one or more ACEs to be added to the specified ACL. The ACEs in the list must be stored contiguously.


### -param AceListLength [in]

Size, in bytes, of the input buffer pointed to by the <i>AceList</i> parameter. 


## -returns



<b>RtlAddAce</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The new ACEs do not fit into the ACL. A larger ACL buffer is required. STATUS_BUFFER_TOO_SMALL is an error code. 

</td>
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
The specified revision is unknown, is not compatible with revisions in the ACE list, or is not compatible with the revision of the ACL. 

</li>
</ul>
STATUS_INVALID_PARAMETER is an error code. 

</td>
</tr>
</table>
 




## -remarks



For information about calculating the size of an ACL, see the Remarks section of the reference entry for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlcreateacl">RtlCreateAcl</a>. 

To obtain a pointer to an ACE in an ACL, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlgetace">RtlGetAce</a>. 

To delete an ACE from an ACL, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtldeleteace">RtlDeleteAce</a>. 

To add an access-allowed ACE to an ACL, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtladdaccessallowedace">RtlAddAccessAllowedAce</a>. 

For more information about security and access control, see the Microsoft Windows Software Development Kit (SDK) for Windows 7 and .NET Framework 4.0 documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/ace">ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtladdaccessallowedace">RtlAddAccessAllowedAce</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlcreateacl">RtlCreateAcl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtldeleteace">RtlDeleteAce</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlgetace">RtlGetAce</a>
 

 

