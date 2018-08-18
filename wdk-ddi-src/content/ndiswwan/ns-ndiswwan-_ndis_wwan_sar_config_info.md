---
UID: NS:ndiswwan._NDIS_WWAN_SAR_CONFIG_INFO
title: _NDIS_WWAN_SAR_CONFIG_INFO
author: windows-driver-content
description: 
ms.assetid: a5a682b3-b08c-4525-a7f2-dec9df51590c
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NDIS_WWAN_SAR_CONFIG_INFO, NDIS_WWAN_SAR_CONFIG_INFO, *PNDIS_WWAN_SAR_CONFIG_INFO, 
req.header: ndiswwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NDIS_WWAN_SAR_CONFIG_INFO, *PNDIS_WWAN_SAR_CONFIG_INFO
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ndiswwan.h
api_name: 
-	_NDIS_WWAN_SAR_CONFIG_INFO
product: Windows
targetos: Windows
---

# _NDIS_WWAN_SAR_CONFIG_INFO structure

## -description


## -struct-fields

The NDIS_WWAN_SAR_CONFIG_INFO describes a modem's current Specific Absorption Rate (SAR) configuration information. It is used in the [NDIS_STATUS_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-sar-config) status notification in response to a previous [OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-config) Query or Set request.

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_BASE_STATIONS_INFO structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.
Header submember
Value
Type 
NDIS_OBJECT_TYPE_DEFAULT 
Revision 
NDIS_WWAN_BASE_STATIONS_INFO_REVISION_1 
Size 
sizeof(NDIS_WWAN_BASE_STATIONS_INFO) 
For more information about these members, see NDIS_OBJECT_HEADER.
 
### -field uStatus
 
### -field SarConfig
 

## -remarks

## -see-also