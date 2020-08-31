---
UID: NF:ntifs.RtlAddAccessAllowedAceEx
title: RtlAddAccessAllowedAceEx function (ntifs.h)
description: The RtlAddAccessAllowedAceEx routine adds an access-allowed access control entry (ACE) with inheritance ACE flags to an access control list (ACL). The access is granted to the specified security identifier (SID).
old-location: ifsk\rtladdaccessallowedaceex.htm
tech.root: ifsk
ms.assetid: aeef74d8-d4a5-4ce4-b7f8-e2a2d263a678
ms.date: 04/16/2018
keywords: ["RtlAddAccessAllowedAceEx function"]
ms.keywords: RtlAddAccessAllowedAceEx, RtlAddAccessAllowedAceEx routine [Installable File System Drivers], ifsk.rtladdaccessallowedaceex, ntifs/RtlAddAccessAllowedAceEx, rtlref_c28640a5-62e2-462a-9c30-b59faedc8386.xml
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available in Microsoft Windows 2000 and later Windows operating systems.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlAddAccessAllowedAceEx
 - ntifs/RtlAddAccessAllowedAceEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlAddAccessAllowedAceEx
---

# RtlAddAccessAllowedAceEx function


## -description

The <b>RtlAddAccessAllowedAceEx</b> routine adds an access-allowed access control entry (<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/ace">ACE</a>) with inheritance ACE flags to an access control list (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>). The access is granted to the specified security identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>).

## -parameters

### -param Acl 

[in, out]
A pointer to a caller-allocated buffer that contains the ACL to be modified. <b>RtlAddAccessAllowedAceEx</b> adds an access-allowed ACE to the end of this ACL. The ACE is in the form of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_access_allowed_ace">ACCESS_ALLOWED_ACE</a> structure.

### -param AceRevision 

[in]
ACL revision level of the ACE to be added. This value can be ACL_REVISION or ACL_REVISION_DS. It must be ACL_REVISION_DS if the ACL contains an object-specific ACE.

### -param AceFlags 

[in]
Bitmask specifying the inherit flags of the ACE to be added.

### -param AccessMask 

[in]
A bitmask of one or more <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> flags that specify the access rights to be granted to the specified SID. For more information, see the description of the <i>DesiredAccess</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>.

### -param Sid 

[in]
A pointer to the SID structure that represents a user, group, or logon account that is being granted access.

## -returns

<b>RtlAddAccessAllowedAceEx</b> can return one of the following values:

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
A new ACE does not fit into the ACL. A larger ACL buffer is required. For more information about how to calculate the size of an ACL, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreateacl">RtlCreateAcl</a>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_ACL</b></dt>
</dl>
</td>
<td width="60%">
The specified ACL is not correctly formed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The AceFlags parameter was invalid.

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
The specified <i>AceRevision</i> is not known or is not compatible with that of the ACL. 

</td>
</tr>
</table>

## -remarks

Unlike <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtladdaccessallowedace">RtlAddAccessAllowedAce</a>, this routine sets the inheritance ACE flags.  

For more information about security and access control, see the documentation about these topics in the Microsoft Windows SDK, such as:

<ul>
<li>
<a href="https://go.microsoft.com/fwlink/p/?linkid=140858">Access Control Lists</a>

</li>
<li>
<a href="https://go.microsoft.com/fwlink/p/?linkid=140859">Creating or Modifying an ACL</a>

</li>
<li>
<a href="https://go.microsoft.com/fwlink/p/?linkid=140860">Getting Information from an ACL</a>

</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_access_allowed_ace">ACCESS_ALLOWED_ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/ace">ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreateacl">RtlCreateAcl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcreatesecuritydescriptor">RtlCreateSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreatesecuritydescriptorrelative">RtlCreateSecurityDescriptorRelative</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtllengthsecuritydescriptor">RtlLengthSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlsetdaclsecuritydescriptor">RtlSetDaclSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsetownersecuritydescriptor">RtlSetOwnerSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlvalidsecuritydescriptor">RtlValidSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-seassignsecurity">SeAssignSecurity</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>

