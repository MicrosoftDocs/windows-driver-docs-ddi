---
UID: NS:ntifs._SYSTEM_SCOPED_POLICY_ID_ACE
title: "_SYSTEM_SCOPED_POLICY_ID_ACE"
description: The SYSTEM_SCOPED_POLICY_ID_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying rights for a scoped policy identifer.
old-location: ifsk\system_scoped_policy_id_ace.htm
tech.root: ifsk
ms.assetid: 2867CA25-B140-4EBA-A8F9-57C12C3700CF
ms.date: 04/16/2018
ms.keywords: "*PSYSTEM_SCOPED_POLICY_ID_ACE, PSYSTEM_SCOPED_POLICY_ID_ACE, PSYSTEM_SCOPED_POLICY_ID_ACE structure pointer [Installable File System Drivers], SYSTEM_SCOPED_POLICY_ID_ACE, SYSTEM_SCOPED_POLICY_ID_ACE structure [Installable File System Drivers], _SYSTEM_SCOPED_POLICY_ID_ACE, ifsk.system_scoped_policy_id_ace, ntifs/PSYSTEM_SCOPED_POLICY_ID_ACE, ntifs/SYSTEM_SCOPED_POLICY_ID_ACE"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	SYSTEM_SCOPED_POLICY_ID_ACE
product:
- Windows
targetos: Windows
req.typenames: SYSTEM_SCOPED_POLICY_ID_ACE, *PSYSTEM_SCOPED_POLICY_ID_ACE
---

# _SYSTEM_SCOPED_POLICY_ID_ACE structure


## -description


The SYSTEM_SCOPED_POLICY_ID_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying  rights for a scoped policy identifer. This ACE causes an audit message to be logged when an atrempt to gain access to an object  based on a configured policy scope.


## -struct-fields




### -field Header

Specifies an ACE_HEADER structure. 


### -field Mask

Specifies an ACCESS_MASK structure that specifies access rights for the scoped policy identifier. 


### -field SidStart

Specifies a SID. The SID represents a scoped policy configured to control access to an object or group of objects.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538847">ACE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>
 

 

