---
UID: NS:ntifs._SYSTEM_SCOPED_POLICY_ID_ACE
title: "_SYSTEM_SCOPED_POLICY_ID_ACE"
author: windows-driver-content
description: The SYSTEM_SCOPED_POLICY_ID_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying rights for a scoped policy identifer.
old-location: ifsk\system_scoped_policy_id_ace.htm
old-project: ifsk
ms.assetid: 2867CA25-B140-4EBA-A8F9-57C12C3700CF
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PSYSTEM_SCOPED_POLICY_ID_ACE, ,, A, C, D, E, I, L, M, O, P, PSYSTEM_SCOPED_POLICY_ID_ACE, PSYSTEM_SCOPED_POLICY_ID_ACE structure pointer [Installable File System Drivers], S, SYSTEM_SCOPED_POLICY_ID_ACE, SYSTEM_SCOPED_POLICY_ID_ACE structure [Installable File System Drivers], T, Y, _, _SYSTEM_SCOPED_POLICY_ID_ACE, ifsk.system_scoped_policy_id_ace, ntifs/PSYSTEM_SCOPED_POLICY_ID_ACE, ntifs/SYSTEM_SCOPED_POLICY_ID_ACE"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	SYSTEM_SCOPED_POLICY_ID_ACE
product: Windows
targetos: Windows
req.typenames: SYSTEM_SCOPED_POLICY_ID_ACE, *PSYSTEM_SCOPED_POLICY_ID_ACE
---

# _SYSTEM_SCOPED_POLICY_ID_ACE structure


## -description


The SYSTEM_SCOPED_POLICY_ID_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying  rights for a scoped policy identifer. This ACE causes an audit message to be logged when an atrempt to gain access to an object  based on a configured policy scope.


## -syntax


````
typedef struct _SYSTEM_SCOPED_POLICY_ID_ACE {
  ACE_HEADER  Header;
  ACCESS_MASK Mask;
  ULONG       SidStart;
} SYSTEM_SCOPED_POLICY_ID_ACE, *PSYSTEM_SCOPED_POLICY_ID_ACE;
````


## -struct-fields




### -field Header

Specifies an ACE_HEADER structure. 


### -field Mask

Specifies an ACCESS_MASK structure that specifies access rights for the scoped policy identifier. 


### -field SidStart

Specifies a SID. The SID represents a scoped policy configured to control access to an object or group of objects.


## -see-also

<a href="..\wdm\ns-wdm-_acl.md">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\ntifs\ns-ntifs-_ace_header.md">ACE_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SYSTEM_SCOPED_POLICY_ID_ACE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

