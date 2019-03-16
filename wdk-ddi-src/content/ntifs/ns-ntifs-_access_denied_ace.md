---
UID: NS:ntifs._ACCESS_DENIED_ACE
title: _ACCESS_DENIED_ACE (ntifs.h)
description: The ACCESS_DENIED_ACE structure defines an access-control entry (ACE) for the discretionary access-control list (DACL) controlling access to an object.
old-location: ifsk\access_denied_ace.htm
tech.root: ifsk
ms.assetid: a7030210-2907-45c7-a689-5e41db7c81b0
ms.date: 04/16/2018
ms.keywords: "*PACCESS_DENIED_ACE, ACCESS_DENIED_ACE, ACCESS_DENIED_ACE structure [Installable File System Drivers], PACCESS_DENIED_ACE, PACCESS_DENIED_ACE structure pointer [Installable File System Drivers], _ACCESS_DENIED_ACE, ifsk.access_denied_ace, ntifs/ACCESS_DENIED_ACE, ntifs/PACCESS_DENIED_ACE, securitystructures_d2c690e3-53bc-4d57-b1b5-1a34ef612a7b.xml"
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- ACCESS_DENIED_ACE
product:
- Windows
targetos: Windows
req.typenames: ACCESS_DENIED_ACE
---

# _ACCESS_DENIED_ACE structure


## -description


The ACCESS_DENIED_ACE structure defines an access-control entry (<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>) for the discretionary access-control list (DACL) controlling access to an object. An access-denied ACE denies access to an object for a specific subject identified by a security identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>). 


## -struct-fields




### -field Header

Specifies an ACE_HEADER structure. 


### -field Mask

ACCESS_MASK structure specifying the access rights explicitly denied by this ACE. 


### -field SidStart

Specifies a SID. The access rights specified by the <b>Mask</b> member are denied to any subject possessing an enabled SID matching this member. 


## -remarks



This structure must be aligned on a 32-bit boundary. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538796">ACCESS_ALLOWED_ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538847">ACE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556769">SYSTEM_ALARM_ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556771">SYSTEM_AUDIT_ACE</a>
 

 

