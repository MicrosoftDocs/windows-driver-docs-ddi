---
UID: NS:iscsidef._ISCSI_TargetPortal
title: _ISCSI_TargetPortal (iscsidef.h)
description: The ISCSI_TargetPortal structure provides a definition of a target portal.
old-location: storage\iscsi_targetportal.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ISCSI_TargetPortal structure"]
ms.keywords: "*PISCSI_TargetPortal, ISCSI_TargetPortal, ISCSI_TargetPortal structure [Storage Devices], PISCSI_TargetPortal, PISCSI_TargetPortal structure pointer [Storage Devices], _ISCSI_TargetPortal, iscsidef/ISCSI_TargetPortal, iscsidef/PISCSI_TargetPortal, storage.iscsi_targetportal, structs-iSCSI_fcbc99fd-e52d-45f4-b525-03c2d925f382.xml"
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
targetos: Windows
req.typenames: ISCSI_TargetPortal, *PISCSI_TargetPortal
f1_keywords:
 - _ISCSI_TargetPortal
 - iscsidef/_ISCSI_TargetPortal
 - PISCSI_TargetPortal
 - iscsidef/PISCSI_TargetPortal
 - ISCSI_TargetPortal
 - iscsidef/ISCSI_TargetPortal
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsidef.h
api_name:
 - _ISCSI_TargetPortal
 - PISCSI_TargetPortal
 - ISCSI_TargetPortal
---

# _ISCSI_TargetPortal structure


## -description

The ISCSI_TargetPortal structure provides a definition of a target portal.

## -struct-fields

### -field Address

A <a href="/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a> structure that indicates the IP address of the portal. The ISCSI_IP_Address structure provides a way to define an IP address that is independent of the version of the IP protocol that the initiator and the target use.

### -field Reserved

Reserved for Microsoft use only.

### -field Socket

Socket number associated with the target.

## -see-also

<a href="/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a>



<a href="/windows-hardware/drivers/storage/iscsi-targetportal-wmi-class">ISCSI_TargetPortal WMI Class</a>

