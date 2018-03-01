---
UID: NF:ntifs.RtlGetDaclSecurityDescriptor
title: RtlGetDaclSecurityDescriptor function
author: windows-driver-content
description: The RtlGetDaclSecurityDescriptor routine returns a pointer to the discretionary ACL (DACL) for a security descriptor.
old-location: ifsk\rtlgetdaclsecuritydescriptor.htm
old-project: ifsk
ms.assetid: 23184d88-2c84-4fba-9d17-c4014d0eaea5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlGetDaclSecurityDescriptor, RtlGetDaclSecurityDescriptor routine [Installable File System Drivers], ifsk.rtlgetdaclsecuritydescriptor, ntifs/RtlGetDaclSecurityDescriptor, rtlref_c851a07b-d480-47a7-b0f7-a3f21161dfaa.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlGetDaclSecurityDescriptor
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlGetDaclSecurityDescriptor function


## -description


The <b>RtlGetDaclSecurityDescriptor</b> routine returns a pointer to the discretionary ACL (DACL) for a security descriptor.


## -syntax


````
NTSTATUS RtlGetDaclSecurityDescriptor(
  _In_  PSECURITY_DESCRIPTOR SecurityDescriptor,
  _Out_ PBOOLEAN             DaclPresent,
  _Out_ PACL                 *Dacl,
  _Out_ PBOOLEAN             DaclDefaulted
);
````


## -parameters




### -param SecurityDescriptor [in]

Pointer to the <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> whose DACL is to be returned.


### -param DaclPresent [out]

Pointer to a Boolean variable that indicates the presence of a DACL in the specified security descriptor. If this variable receives <b>TRUE</b>, the security descriptor contains a DACL, and the remaining output parameters receive valid values. If this variable receives <b>FALSE</b>, the security descriptor does not contain a DACL, and the remaining output parameters do not receive valid values.


### -param Dacl [out]

Pointer to a variable that receives the address of the DACL for the security descriptor. If the security descriptor does not have a DACL, this variable does not receive a value. If the security descriptor has a <b>NULL</b> DACL, this variable receives <b>NULL</b>. A <b>NULL</b> DACL implicitly allows all access to an object.


### -param DaclDefaulted [out]

Pointer to a Boolean variable that receives the value of the SE_DACL_DEFAULTED flag in the security descriptor's SECURITY_DESCRIPTOR_CONTROL structure. If this flag is <b>TRUE</b>, the DACL was retrieved by a default mechanism. If it is <b>FALSE</b>, the DACL was explicitly specified by a user. This value is valid only if <i>*Dacl</i> receives a non-<b>NULL</b> value. 


## -returns



<b>RtlGetDaclSecurityDescriptor</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>
</td>
<td width="60%">
The security descriptor's revision level is unknown or is not supported. This is an error code.

</td>
</tr>
</table>
 




## -remarks



A value of <b>TRUE</b> for <i>*DaclPresent</i> does not mean that <i>*Dacl</i> is non-<b>NULL</b>. That is, <i>*DaclPresent</i> can be <b>TRUE</b> while <i>*Dacl</i> is <b>NULL</b>, meaning that a <b>NULL</b> DACL is in effect. A <b>NULL</b> DACL implicitly allows all access to an object and is not the same as an empty DACL. An empty DACL permits no access to an object. 

For more information about security and access control, see the documentation for these topics in the Microsoft Windows SDK. 




## -see-also

<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>



<a href="..\wdm\ns-wdm-_acl.md">ACL</a>



<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>



<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlGetDaclSecurityDescriptor routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

