---
UID: NS:ntifs._SECURITY_DESCRIPTOR
title: "_SECURITY_DESCRIPTOR"
author: windows-driver-content
description: The SECURITY_DESCRIPTOR structure specifies the security information that is associated with an object. For more information, see the reference page for SECURITY_DESCRIPTOR in the Installable File System documentation.
old-location: kernel\security_descriptor.htm
old-project: kernel
ms.assetid: 0af0685c-d3a3-4c76-8fca-fb38f60411bf
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PISECURITY_DESCRIPTOR, SECURITY_DESCRIPTOR, SECURITY_DESCRIPTOR structure [Kernel-Mode Driver Architecture], _SECURITY_DESCRIPTOR, kernel.security_descriptor, kstruct_d_0b8cd06a-644b-40a4-b2bb-6c8c74d63db8.xml, wdm/SECURITY_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	SECURITY_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: SECURITY_DESCRIPTOR, *PISECURITY_DESCRIPTOR
---

# _SECURITY_DESCRIPTOR structure


## -description


The <b>SECURITY_DESCRIPTOR</b> structure specifies the security information that is associated with an object. For more information, see the reference page for <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> in the Installable File System documentation.


## -struct-fields


## -see-also

<a href="..\wdm\nf-wdm-obgetobjectsecurity.md">ObGetObjectSecurity</a>



<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-seaccesscheck.md">SeAccessCheck</a>



<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-sedeassignsecurity.md">SeDeassignSecurity</a>



<a href="..\wdm\nf-wdm-obreleaseobjectsecurity.md">ObReleaseObjectSecurity</a>



<a href="..\wdm\nf-wdm-seassignsecurity.md">SeAssignSecurity</a>



<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>



 

 


