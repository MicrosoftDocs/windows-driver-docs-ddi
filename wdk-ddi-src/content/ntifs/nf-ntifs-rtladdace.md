---
UID: NF:ntifs.RtlAddAce
title: RtlAddAce function
author: windows-driver-content
description: The RtlAddAce routine adds one or more access control entries (ACEs) to a specified access control list (ACL).
old-location: ifsk\rtladdace.htm
old-project: ifsk
ms.assetid: 291b1fa9-5f42-49b6-b6de-20054a832bb2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/RtlAddAce, rtlref_798d31d8-c233-4154-981d-a84cfdd95045.xml, RtlAddAce routine [Installable File System Drivers], ifsk.rtladdace, RtlAddAce
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlAddAce
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlAddAce function


## -description


The <b>RtlAddAce</b> routine adds one or more access control entries (ACEs) to a specified access control list (ACL).


## -syntax


````
NTSTATUS RtlAddAce(
  _Inout_ PACL  Acl,
  _In_    ULONG AceRevision,
  _In_    ULONG StartingAceIndex,
  _In_    PVOID AceList,
  _In_    ULONG AceListLength
);
````


## -parameters




#### - Acl [in, out]

Pointer to the ACL to be modified. <b>RtlAddAce</b> adds the specified ACEs to this ACL. 


#### - AceRevision [in]

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


#### - StartingAceIndex [in]

Specifies the position in the ACL's list of ACEs at which to add new ACEs. A value of zero inserts the ACEs at the beginning of the list. A value of MAXULONG appends the ACEs to the end of the list.


#### - AceList [in]

Pointer to a buffer containing a list of one or more ACEs to be added to the specified ACL. The ACEs in the list must be stored contiguously.


#### - AceListLength [in]

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


For information about calculating the size of an ACL, see the Remarks section of the reference entry for <a href="..\ntifs\nf-ntifs-rtlcreateacl.md">RtlCreateAcl</a>. 

To obtain a pointer to an ACE in an ACL, use <a href="..\ntifs\nf-ntifs-rtlgetace.md">RtlGetAce</a>. 

To delete an ACE from an ACL, use <a href="..\ntifs\nf-ntifs-rtldeleteace.md">RtlDeleteAce</a>. 

To add an access-allowed ACE to an ACL, use <a href="..\ntifs\nf-ntifs-rtladdaccessallowedace.md">RtlAddAccessAllowedAce</a>. 

For more information about security and access control, see the Microsoft Windows Software Development Kit (SDK) for Windows 7 and .NET Framework 4.0 documentation.



## -see-also

<a href="..\ntifs\nf-ntifs-rtlgetace.md">RtlGetAce</a>

<a href="..\ntifs\nf-ntifs-rtldeleteace.md">RtlDeleteAce</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>

<a href="..\ntifs\nf-ntifs-rtlcreateacl.md">RtlCreateAcl</a>

<a href="..\ntifs\nf-ntifs-rtladdaccessallowedace.md">RtlAddAccessAllowedAce</a>

<a href="..\wdm\ns-wdm-_acl.md">ACL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlAddAce routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

