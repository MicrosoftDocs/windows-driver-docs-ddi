---
UID: NS:ntifs._SECURITY_DESCRIPTOR
title: "_SECURITY_DESCRIPTOR"
author: windows-driver-content
description: The SECURITY_DESCRIPTOR structure contains the security information associated with an object. Drivers use this structure to set and query an object's security status.
old-location: ifsk\security_descriptor.htm
old-project: ifsk
ms.assetid: f0758549-0c3f-4aa3-8107-59503645f270
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PISECURITY_DESCRIPTOR, SECURITY_DESCRIPTOR, SECURITY_DESCRIPTOR structure [Installable File System Drivers], _SECURITY_DESCRIPTOR, ifsk.security_descriptor, ntifs/SECURITY_DESCRIPTOR, securitystructures_b3cd4d20-6abc-49e7-92dd-8dd707e973fa.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Microsoft Windows 2000.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	SECURITY_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: SECURITY_DESCRIPTOR, *PISECURITY_DESCRIPTOR
---

# _SECURITY_DESCRIPTOR structure


## -description


The SECURITY_DESCRIPTOR structure contains the security information associated with an object. Drivers use this structure to set and query an object's security status. 

Because the internal format of a security descriptor can vary, drivers are not to modify the SECURITY_DESCRIPTOR structure directly. For creating and manipulating a security descriptor, use the functions listed in the See Also section. 


## -struct-fields




### -field Revision


### -field Sbz1


### -field Control


### -field Owner


### -field Group


### -field Sacl


### -field Dacl


## -remarks



A security descriptor includes information that specifies the following components of an object's security: 

<ul>
<li>
An owner (<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>) 

</li>
<li>
A primary group (SID) 

</li>
<li>
A discretionary <a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a> (DACL) 

</li>
<li>
A system ACL (SACL) 

</li>
</ul>
Qualifiers for the preceding items 

Requirements: ntifs.h (include ntifs.h)




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557738">ObGetObjectSecurity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558695">ObReleaseObjectSecurity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561827">RtlCreateSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552976">RtlGetOwnerSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562025">RtlLengthSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562781">RtlSetDaclSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553220">RtlSetOwnerSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563024">RtlValidSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556619">SECURITY_DESCRIPTOR_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563674">SeAccessCheck</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563676">SeAssignSecurity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563679">SeAssignSecurityEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563716">SeDeassignSecurity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556709">SeSetSecurityDescriptorInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556712">SeSetSecurityDescriptorInfoEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563793">SeValidSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567066">ZwQuerySecurityObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567106">ZwSetSecurityObject</a>
 

 

