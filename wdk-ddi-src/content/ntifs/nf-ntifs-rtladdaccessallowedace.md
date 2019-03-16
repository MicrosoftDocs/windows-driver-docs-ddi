---
UID: NF:ntifs.RtlAddAccessAllowedAce
title: RtlAddAccessAllowedAce function (ntifs.h)
description: The RtlAddAccessAllowedAce routine adds an access-allowed access control entry (ACE) to an access control list (ACL). The access is granted to the specified security identifier (SID).
old-location: ifsk\rtladdaccessallowedace.htm
tech.root: ifsk
ms.assetid: 39a50efc-b27a-4c73-b436-c6495256d9c6
ms.date: 04/16/2018
ms.keywords: RtlAddAccessAllowedAce, RtlAddAccessAllowedAce routine [Installable File System Drivers], ifsk.rtladdaccessallowedace, ntifs/RtlAddAccessAllowedAce, rtlref_ab4b97bd-c68c-4f7b-a50e-8584f53e6720.xml
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlAddAccessAllowedAce
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlAddAccessAllowedAce function


## -description


The <b>RtlAddAccessAllowedAce</b> routine adds an access-allowed access control entry (ACE) to an access control list (ACL). The access is granted to the specified security identifier (SID). 


## -parameters




### -param Acl [in, out]

Pointer to a caller-allocated buffer containing the ACL to be modified. <b>RtlAddAccessAllowedAce</b> adds an access-allowed ACE to the end of this ACL. The ACE is in the form of an ACCESS_ALLOWED_ACE structure.


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
 


### -param AccessMask [in]

Bitmask of one or more <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> flags specifying the access rights to be granted to the specified SID. For more information, see the description of the <i>DesiredAccess</i> parameter of <b>ZwCreateFile</b>. 


### -param Sid [in]

Pointer to the SID structure representing a user, group, or logon account that is being granted access. 


## -returns



<b>RtlAddAccessAllowedAce</b> can return one of the following values:

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
The ACE was successfully added.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ALLOTTED_SPACE_EXCEEDED</b></dt>
</dl>
</td>
<td width="60%">
A new ACE does not fit into the ACL. A larger ACL buffer is required. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff552151">RtlCreateAcl</a> for information about calculating the size of an ACL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_ACL</b></dt>
</dl>
</td>
<td width="60%">
The specified ACL is not properly formed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_SID</b></dt>
</dl>
</td>
<td width="60%">
The specified SID structure is not structurally valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REVISION_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The specified revision is not known or is not compatible with that of the ACL. 

</td>
</tr>
</table>
 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows Software Development Kit (SDK) for Windows 7 and .NET Framework 4.0.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538796">ACCESS_ALLOWED_ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552151">RtlCreateAcl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561827">RtlCreateSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552165">RtlCreateSecurityDescriptorRelative</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562025">RtlLengthSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562781">RtlSetDaclSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553220">RtlSetOwnerSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563024">RtlValidSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563676">SeAssignSecurity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>
 

 

