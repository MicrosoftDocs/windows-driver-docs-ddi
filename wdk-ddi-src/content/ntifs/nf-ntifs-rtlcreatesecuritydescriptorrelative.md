---
UID: NF:ntifs.RtlCreateSecurityDescriptorRelative
title: RtlCreateSecurityDescriptorRelative function
author: windows-driver-content
description: The RtlCreateSecurityDescriptorRelative routine initializes a new security descriptor in self-relative format.
old-location: ifsk\rtlcreatesecuritydescriptorrelative.htm
old-project: ifsk
ms.assetid: feb9600a-e8ce-449a-8da8-2d9a2f10f581
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlCreateSecurityDescriptorRelative
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlCreateSecurityDescriptorRelative
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
req.irql: PASSIVE_LEVEL
req.typenames: TOKEN_TYPE
---

# RtlCreateSecurityDescriptorRelative function



## -description
The <b>RtlCreateSecurityDescriptorRelative</b> routine initializes a new security descriptor in self-relative format. On return, the security descriptor is initialized with no system ACL (SACL), no discretionary ACL (DACL), no owner, no primary group, and all control flags set to zero.



## -syntax

````
NTSTATUS RtlCreateSecurityDescriptorRelative(
  _Out_ PISECURITY_DESCRIPTOR_RELATIVE SecurityDescriptor,
  _In_  ULONG                          Revision
);
````


## -parameters

### -param SecurityDescriptor [out]

Pointer to a caller-allocated buffer, which must be at least <b>sizeof</b>(SECURITY_DESCRIPTOR_RELATIVE), to receive the initialized security descriptor. 


### -param Revision [in]

Revision level to assign to the security descriptor. This parameter must be SECURITY_DESCRIPTOR_REVISION.


## -returns
<b>RtlCreateSecurityDescriptorRelative</b> can return one of the following:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The call completed successfully.
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>The given <i>Revision</i> is not known or is not supported.

 


## -remarks
In effect, a successful call to this routine initializes a security descriptor without security constraints.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_acl.md">ACL</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md">RtlSetOwnerSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlCreateSecurityDescriptorRelative routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

