---
UID: NS:iscsidef._ISCSI_TargetPortal
title: "_ISCSI_TargetPortal"
description: The ISCSI_TargetPortal structure provides a definition of a target portal.
old-location: storage\iscsi_targetportal.htm
tech.root: storage
ms.assetid: 1adb1dbf-3ec4-4e32-bfe8-cfcf992f67ca
ms.date: 03/29/2018
ms.keywords: "*PISCSI_TargetPortal, ISCSI_TargetPortal, ISCSI_TargetPortal structure [Storage Devices], PISCSI_TargetPortal, PISCSI_TargetPortal structure pointer [Storage Devices], _ISCSI_TargetPortal, iscsidef/ISCSI_TargetPortal, iscsidef/PISCSI_TargetPortal, storage.iscsi_targetportal, structs-iSCSI_fcbc99fd-e52d-45f4-b525-03c2d925f382.xml"
ms.topic: struct
req.header: iscsidef.h
req.include-header: Iscsidef.h
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
-	iscsidef.h
api_name:
-	ISCSI_TargetPortal
product:
- Windows
targetos: Windows
req.typenames: ISCSI_TargetPortal, *PISCSI_TargetPortal
---

# _ISCSI_TargetPortal structure


## -description


The ISCSI_TargetPortal structure provides a definition of a target portal. 


## -struct-fields




### -field Address

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a> structure that indicates the IP address of the portal. The ISCSI_IP_Address structure provides a way to define an IP address that is independent of the version of the IP protocol that the initiator and the target use.


### -field Reserved

Reserved for Microsoft use only. 


### -field Socket

Socket number associated with the target.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561577">ISCSI_TargetPortal WMI Class</a>
 

 

