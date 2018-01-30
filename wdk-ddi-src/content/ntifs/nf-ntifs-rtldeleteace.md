---
UID: NF:ntifs.RtlDeleteAce
title: RtlDeleteAce function
author: windows-driver-content
description: The RtlDeleteAce routine deletes an access control entry (ACE) from a specified access control list (ACL).
old-location: ifsk\rtldeleteace.htm
old-project: ifsk
ms.assetid: 2bf90d1d-887f-4d0c-8d79-e102a14dfe71
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.rtldeleteace, ntifs/RtlDeleteAce, RtlDeleteAce, rtlref_68fe46f1-318a-48c6-9004-c338f52f41a5.xml, RtlDeleteAce routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlDeleteAce
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlDeleteAce function


## -description


The <b>RtlDeleteAce</b> routine deletes an access control entry (ACE) from a specified access control list (ACL).


## -syntax


````
NTSTATUS RtlDeleteAce(
  _Inout_ PACL  Acl,
  _In_    ULONG AceIndex
);
````


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


For information about calculating the size of an ACL, see the Remarks section of the reference entry for <a href="..\ntifs\nf-ntifs-rtlcreateacl.md">RtlCreateAcl</a>. 

To add an ACE to an ACL, use <a href="..\ntifs\nf-ntifs-rtladdace.md">RtlAddAce</a>. 

To obtain a pointer to an ACE in an ACL, use <a href="..\ntifs\nf-ntifs-rtlgetace.md">RtlGetAce</a>. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 



## -see-also

<a href="..\ntifs\nf-ntifs-rtladdace.md">RtlAddAce</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>

<a href="..\ntifs\nf-ntifs-rtlcreateacl.md">RtlCreateAcl</a>

<a href="..\ntifs\nf-ntifs-rtlgetace.md">RtlGetAce</a>

<a href="..\wdm\ns-wdm-_acl.md">ACL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlDeleteAce routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

