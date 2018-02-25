---
UID: NF:ntifs.RtlAbsoluteToSelfRelativeSD
title: RtlAbsoluteToSelfRelativeSD function
author: windows-driver-content
description: The RtlAbsoluteToSelfRelativeSD routine creates a new security descriptor in self-relative format by using a security descriptor in absolute format as a template.
old-location: ifsk\rtlabsolutetoselfrelativesd.htm
old-project: ifsk
ms.assetid: e6247856-5abf-44ea-afe8-9be3f61271a4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, D, R, RtlAbsoluteToSelfRelativeSD, RtlAbsoluteToSelfRelativeSD routine [Installable File System Drivers], S, T, a, b, e, f, i, ifsk.rtlabsolutetoselfrelativesd, l, ntifs/RtlAbsoluteToSelfRelativeSD, o, rtlref_809e562f-be24-43d2-8357-ffd83eac421a.xml, s, t, u, v"
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
-	RtlAbsoluteToSelfRelativeSD
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlAbsoluteToSelfRelativeSD function


## -description


The <b>RtlAbsoluteToSelfRelativeSD</b> routine creates a new security descriptor in self-relative format by using a security descriptor in absolute format as a template. 


## -syntax


````
NTSTATUS RtlAbsoluteToSelfRelativeSD(
  _In_    PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor,
  _Out_   PSECURITY_DESCRIPTOR SelfRelativeSecurityDescriptor,
  _Inout_ PULONG               BufferLength
);
````


## -parameters




### -param AbsoluteSecurityDescriptor [in]

Pointer to a caller-allocated buffer that contains a <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure in absolute format. <b>RtlAbsoluteToSelfRelativeSD</b> creates a version of this security descriptor in self-relative format without modifying the original. 


### -param SelfRelativeSecurityDescriptor [out]

Pointer to a caller-allocated buffer that receives a security descriptor in self-relative format. 


### -param BufferLength [in, out]

Pointer to a caller-allocated variable that specifies the size, in bytes, of the buffer pointed to by the <i>SelfRelativeSecurityDescriptor</i> parameter. If the buffer is not large enough to hold the security descriptor, <b>RtlAbsoluteToSelfRelativeSD</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the minimum required size. 


## -returns



<b>RtlAbsoluteToSelfRelativeSD</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BAD_DESCRIPTOR_FORMAT</b></dt>
</dl>
</td>
<td width="60%">
The buffer pointed to by the <i>AbsoluteSecurityDescriptor</i> parameter did not contain a SECURITY_DESCRIPTOR structure in absolute format. STATUS_BAD_DESCRIPTOR_FORMAT is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer pointed to by the <i>SelfRelativeSecurityDescriptor</i> parameter was too small to contain the security descriptor in self-relative format. STATUS_BUFFER_TOO_SMALL is an error code. 

</td>
</tr>
</table>
 




## -remarks



A security descriptor in absolute format contains pointers to the information it contains, rather than containing the information itself. A security descriptor in self-relative format contains the information in a contiguous block of memory. In a self-relative security descriptor, a <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure always starts the information, but the security descriptor's other components can follow the SECURITY_DESCRIPTOR structure in any order. Instead of using memory addresses, the components of the security descriptor are identified by offsets from the beginning of the security descriptor. This format is useful when a security descriptor must be stored on a disk or transmitted by means of a communications protocol. 

To create a new security descriptor in absolute format by using a security descriptor in self-relative format as a template, use <a href="..\ntifs\nf-ntifs-rtlselfrelativetoabsolutesd.md">RtlSelfRelativeToAbsoluteSD</a>. 

For more information about security and access control, see the Microsoft Windows SDK documentation. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md">RtlSetOwnerSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>



<a href="..\ntifs\nf-ntifs-rtlselfrelativetoabsolutesd.md">RtlSelfRelativeToAbsoluteSD</a>



<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>



<a href="..\wdm\ns-wdm-_acl.md">ACL</a>



<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlAbsoluteToSelfRelativeSD routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

