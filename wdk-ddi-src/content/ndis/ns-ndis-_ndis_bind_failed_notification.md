---
UID: NS:ndis._NDIS_BIND_FAILED_NOTIFICATION
title: _NDIS_BIND_FAILED_NOTIFICATION (ndis.h)
description: The NDIS_BIND_FAILED_NOTIFICATION structure describes a binding event failure.
old-location: netvista\ndis_bind_failed_notification.htm
tech.root: netvista
ms.assetid: 5420839B-EB81-43CC-B7BD-9D1FA2560A3D
ms.date: 05/02/2018
ms.keywords: "*PNDIS_BIND_FAILED_NOTIFICATION, NDIS_BIND_FAILED_NOTIFICATION, NDIS_BIND_FAILED_NOTIFICATION structure [Network Drivers Starting with Windows Vista], PNDIS_BIND_FAILED_NOTIFICATION, PNDIS_BIND_FAILED_NOTIFICATION structure pointer [Network Drivers Starting with Windows Vista], _NDIS_BIND_FAILED_NOTIFICATION, ndis/NDIS_BIND_FAILED_NOTIFICATION, ndis/PNDIS_BIND_FAILED_NOTIFICATION, netvista.ndis_bind_failed_notification"
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
- ndis.h
api_name:
- NDIS_BIND_FAILED_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: NDIS_BIND_FAILED_NOTIFICATION, *PNDIS_BIND_FAILED_NOTIFICATION
---

# _NDIS_BIND_FAILED_NOTIFICATION structure


## -description


The <b>NDIS_BIND_FAILED_NOTIFICATION</b> structure describes a binding event failure.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_BIND_FAILED_NOTIFICATION</b> structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to <b>NDIS_BIND_FAILED_NOTIFICATION_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_BIND_FAILED_NOTIFICATION_REVISION_1</b>.


### -field MiniportNetLuid

The NDIS network interface
     name (<i>ifName</i> in RFC 2863) of the miniport adapter.

