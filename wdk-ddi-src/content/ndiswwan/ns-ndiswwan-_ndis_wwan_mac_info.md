---
UID: NS:ndiswwan._NDIS_WWAN_MAC_INFO
title: _NDIS_WWAN_MAC_INFO (ndiswwan.h)
description: The NDIS_WWAN_MAC_INFO structure represents NDIS port information for a PDP context.
old-location: netvista\ndis_wwan_mac_info.htm
tech.root: netvista
ms.assetid: C55DC50B-5A1B-496E-BBB8-8EB94A9CFD2F
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_MAC_INFO, NDIS_WWAN_MAC_INFO, NDIS_WWAN_MAC_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_MAC_INFO, PNDIS_WWAN_MAC_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_MAC_INFO, ndiswwan/NDIS_WWAN_MAC_INFO, ndiswwan/PNDIS_WWAN_MAC_INFO, netvista.ndis_wwan_mac_info"
ms.topic: struct
f1_keywords:
 - "ndiswwan/NDIS_WWAN_MAC_INFO"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8.1 and later versions of Windows.
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
- ndiswwan.h
api_name:
- NDIS_WWAN_MAC_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_MAC_INFO, *PNDIS_WWAN_MAC_INFO
---

# _NDIS_WWAN_MAC_INFO structure


## -description


The NDIS_WWAN_MAC_INFO structure represents NDIS port information for a PDP context.


## -struct-fields




### -field uReserved

Reserved. Do not use.


### -field uNdisPortNumber

The number of the NDIS port. This value is an NDIS_PORT_NUMBER value, which has a ULONG data type and is valid from zero through 0xffffff, where zero is reserved for the default port.


### -field MacAddr

The NDIS port of the PDP context.

