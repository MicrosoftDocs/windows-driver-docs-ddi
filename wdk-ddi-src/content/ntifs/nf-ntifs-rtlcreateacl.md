---
UID: NF:ntifs.RtlCreateAcl
title: RtlCreateAcl function
author: windows-driver-content
description: The RtlCreateAcl routine creates and initializes an access control list (ACL).
old-location: ifsk\rtlcreateacl.htm
old-project: ifsk
ms.assetid: d7bf1fa0-81e0-4b44-adcd-d8f629453ac8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, C, R, RtlCreateAcl, RtlCreateAcl routine [Installable File System Drivers], a, c, e, ifsk.rtlcreateacl, l, ntifs/RtlCreateAcl, r, rtlref_0b8e6b6c-308f-4acd-b109-d6042964ea7f.xml, t"
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlCreateAcl
product: Windows
targetos: Windows
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


### -param AclRevision

TBD




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
<div class="alert"><b>Note</b>  <i>AceRevision</i> must be ACL_REVISION_DS if the ACL in <i>Acl</i> contains an object-specific ACE.</div>
<div> </div>
</td>
</tr>
</table>
 


## -returns



<b>RtlCreateAcl</b> can return one of the following status values:

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
The ACL was successfully created and initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The new ACL does not fit into the buffer at <i>Acl</i>. A larger ACL buffer is required. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified revision is not current, or the value of <i>AclLength</i> is too large. 

</td>
</tr>
</table>
 




## -remarks



The ACL that is initialized by <b>RtlCreateAcl</b> contains no access control entries (ACE). This ACL is empty, as opposed to being a nonexistent ACL. If an empty ACL is applied to an object, the ACL implicitly denies all access to that object. To add ACEs to the ACL, use <a href="..\ntifs\nf-ntifs-rtladdaccessallowedace.md">RtlAddAccessAllowedAce</a>.

To calculate the size of an ACL, add <b>sizeof</b>(ACL) to the size of all the ACEs to be stored in the ACL. To calculate the size of an ACE, add the size of the ACE structure, such as <b>sizeof</b>(ACCESS_ALLOWED_ACE), to the length of the SID associated with the ACE, and then subtract the size of the <b>SidStart</b> member (which is part of both the ACE structure and the SID). Use the <a href="..\ntifs\nf-ntifs-rtllengthsid.md">RtlLengthSid</a> function to get the length of a specified SID.

The following example shows how to calculate the size of an access-allowed ACE:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>sizeof (ACCESS_ALLOWED_ACE) - sizeof (ACCESS_ALLOWED_ACE.SidStart) 
        + GetLengthSid (pAceSid);</pre>
</td>
</tr>
</table></span></div>
To calculate the size of an ACL, use the following algorithm, substituting the appropriate ACE structure in the <b>sizeof</b>(ACE) expression:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>cbAcl = sizeof (ACL);
for (i = 0 ; i &lt; nAceCount ; i++) {
    // subtract ACE.SidStart from the size
    cbAce = sizeof (ACE) - sizeof (DWORD);
    // add this ACE's SID length
    cbAce += GetLengthSid (pAceSid[i]);
    // add the length of each ACE to the total ACL length
    cbAcl += cbAce;
}</pre>
</td>
</tr>
</table></span></div>
For more information about security and access control, see the documentation on these topics in thePlatform Software Development Kit (SDK).




## -see-also

<a href="..\ntifs\nf-ntifs-rtladdaccessallowedace.md">RtlAddAccessAllowedAce</a>



<a href="..\ntifs\nf-ntifs-rtllengthsid.md">RtlLengthSid</a>



<a href="..\ntifs\ns-ntifs-_access_allowed_ace.md">ACCESS_ALLOWED_ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\wdm\ns-wdm-_acl.md">ACL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlCreateAcl routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

