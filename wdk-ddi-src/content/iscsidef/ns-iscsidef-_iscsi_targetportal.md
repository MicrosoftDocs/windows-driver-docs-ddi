---
UID: NS:iscsidef._ISCSI_TargetPortal
title: "_ISCSI_TargetPortal"
author: windows-driver-content
description: The ISCSI_TargetPortal structure provides a definition of a target portal.
old-location: storage\iscsi_targetportal.htm
old-project: storage
ms.assetid: 1adb1dbf-3ec4-4e32-bfe8-cfcf992f67ca
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PISCSI_TargetPortal, ISCSI_TargetPortal, ISCSI_TargetPortal structure [Storage Devices], PISCSI_TargetPortal, PISCSI_TargetPortal structure pointer [Storage Devices], _ISCSI_TargetPortal, iscsidef/ISCSI_TargetPortal, iscsidef/PISCSI_TargetPortal, storage.iscsi_targetportal, structs-iSCSI_fcbc99fd-e52d-45f4-b525-03c2d925f382.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: ISCSI_TargetPortal, *PISCSI_TargetPortal
---

# _ISCSI_TargetPortal structure


## -description


The ISCSI_TargetPortal structure provides a definition of a target portal. 


## -syntax


````
typedef struct _ISCSI_TargetPortal {
  ISCSI_IP_Address Address;
  ULONG            Reserved;
  USHORT           Socket;
} ISCSI_TargetPortal, *PISCSI_TargetPortal;
````


## -struct-fields




### -field Address

A <a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a> structure that indicates the IP address of the portal. The ISCSI_IP_Address structure provides a way to define an IP address that is independent of the version of the IP protocol that the initiator and the target use.


### -field Reserved

Reserved for Microsoft use only. 


### -field Socket

Socket number associated with the target.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561577">ISCSI_TargetPortal WMI Class</a>



<a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_TargetPortal structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

