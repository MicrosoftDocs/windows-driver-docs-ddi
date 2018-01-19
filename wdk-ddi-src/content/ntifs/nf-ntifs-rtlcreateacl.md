---
UID: NF:ntifs.RtlCreateAcl
title: RtlCreateAcl function
author: windows-driver-content
description: The RtlCreateAcl routine creates and initializes an access control list (ACL).
old-location: ifsk\rtlcreateacl.htm
old-project: ifsk
ms.assetid: d7bf1fa0-81e0-4b44-adcd-d8f629453ac8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlCreateAcl
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
req.alt-api: RtlCreateAcl
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
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# RtlCreateAcl function



## -description
The <b>RtlCreateAcl</b> routine creates and initializes an access control list (ACL). 



## -syntax

````
NTSTATUS RtlCreateAcl(
  _Out_ PACL  Acl,
  _In_  ULONG AclLength,
  _In_  ULONG AceRevision
);
````


## -parameters

### -param Acl [out]

Pointer to a caller-allocated buffer to receive the initialized ACL structure. This buffer must be at least <b>sizeof</b>(ACL),


### -param AclLength [in]

Length, in bytes, of the buffer pointed to by the <i>Acl</i> parameter. This value must be large enough to contain the ACL header and all of the access-control entries (ACE) to be stored in the ACL. See the following Remarks section for information about calculating the size of an ACL. 


### -param AceRevision [in]

ACL revision level of the ACE to be added. Windows version requirments are the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">

### -param ACL_REVISION

</td>
<td width="60%">
The revision level valid on all Windows versions.

</td>
</tr>
<tr>
<td width="40%">

### -param ACL_REVISION_DS

</td>
<td width="60%">
<div class="alert"><b>Note</b>  <i>AceRevision</i> must be ACL_REVISION_DS if the ACL in <i>Acl</i> contains an object-specific ACE.</div>
<div> </div>
</td>
</tr>
</table>
 


## -returns
<b>RtlCreateAcl</b> can return one of the following status values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The ACL was successfully created and initialized.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The new ACL does not fit into the buffer at <i>Acl</i>. A larger ACL buffer is required. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The specified revision is not current, or the value of <i>AclLength</i> is too large. 

 


## -remarks
The ACL that is initialized by <b>RtlCreateAcl</b> contains no access control entries (ACE). This ACL is empty, as opposed to being a nonexistent ACL. If an empty ACL is applied to an object, the ACL implicitly denies all access to that object. To add ACEs to the ACL, use <a href="..\ntifs\nf-ntifs-rtladdaccessallowedace.md">RtlAddAccessAllowedAce</a>.

To calculate the size of an ACL, add <b>sizeof</b>(ACL) to the size of all the ACEs to be stored in the ACL. To calculate the size of an ACE, add the size of the ACE structure, such as <b>sizeof</b>(ACCESS_ALLOWED_ACE), to the length of the SID associated with the ACE, and then subtract the size of the <b>SidStart</b> member (which is part of both the ACE structure and the SID). Use the <a href="..\ntifs\nf-ntifs-rtllengthsid.md">RtlLengthSid</a> function to get the length of a specified SID.

The following example shows how to calculate the size of an access-allowed ACE:

To calculate the size of an ACL, use the following algorithm, substituting the appropriate ACE structure in the <b>sizeof</b>(ACE) expression:

For more information about security and access control, see the documentation on these topics in thePlatform Software Development Kit (SDK).


## -see-also
<dl>
<dt>
<a href="..\ntifs\ns-ntifs-_access_allowed_ace.md">ACCESS_ALLOWED_ACE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_acl.md">ACL</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtladdaccessallowedace.md">RtlAddAccessAllowedAce</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtllengthsid.md">RtlLengthSid</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlCreateAcl routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

