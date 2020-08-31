---
UID: NF:ntifs.RtlCreateSecurityDescriptorRelative
title: RtlCreateSecurityDescriptorRelative function (ntifs.h)
description: The RtlCreateSecurityDescriptorRelative routine initializes a new security descriptor in self-relative format.
old-location: ifsk\rtlcreatesecuritydescriptorrelative.htm
tech.root: ifsk
ms.assetid: feb9600a-e8ce-449a-8da8-2d9a2f10f581
ms.date: 04/16/2018
keywords: ["RtlCreateSecurityDescriptorRelative function"]
ms.keywords: RtlCreateSecurityDescriptorRelative, RtlCreateSecurityDescriptorRelative routine [Installable File System Drivers], ifsk.rtlcreatesecuritydescriptorrelative, ntifs/RtlCreateSecurityDescriptorRelative, rtlref_3130b278-4976-4371-952f-ab6fddeda7a9.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlCreateSecurityDescriptorRelative
 - ntifs/RtlCreateSecurityDescriptorRelative
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlCreateSecurityDescriptorRelative
---

# RtlCreateSecurityDescriptorRelative function


## -description

The <b>RtlCreateSecurityDescriptorRelative</b> routine initializes a new security descriptor in self-relative format. On return, the security descriptor is initialized with no system ACL (SACL), no discretionary ACL (DACL), no owner, no primary group, and all control flags set to zero.

## -parameters

### -param SecurityDescriptor 

[out]
Pointer to a caller-allocated buffer, which must be at least <b>sizeof</b>(SECURITY_DESCRIPTOR_RELATIVE), to receive the initialized security descriptor.

### -param Revision 

[in]
Revision level to assign to the security descriptor. This parameter must be SECURITY_DESCRIPTOR_REVISION.

## -returns

<b>RtlCreateSecurityDescriptorRelative</b> can return one of the following:

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
The call completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>
</td>
<td width="60%">
The given <i>Revision</i> is not known or is not supported.

</td>
</tr>
</table>

## -remarks

In effect, a successful call to this routine initializes a security descriptor without security constraints.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcreatesecuritydescriptor">RtlCreateSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtllengthsecuritydescriptor">RtlLengthSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlsetdaclsecuritydescriptor">RtlSetDaclSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsetownersecuritydescriptor">RtlSetOwnerSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlvalidsecuritydescriptor">RtlValidSecurityDescriptor</a>

