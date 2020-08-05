---
UID: NS:ndiswwan._NDIS_WWAN_SET_SAR_CONFIG
title: _NDIS_WWAN_SET_SAR_CONFIG (ndiswwan.h)
description: The NDIS_WWAN_SET_SAR_CONFIG structure describes Specific Absorption Rate (SAR) information that a mobile broadband (MB) modem should use to set its SAR configuration.
tech.root: netvista
ms.assetid: 1d92e287-b6d5-4eb6-9d34-963331b04a00
ms.date: 08/20/2018
keywords: ["NDIS_WWAN_SET_SAR_CONFIG structure"]
f1_keywords:
 - "ndiswwan/_NDIS_WWAN_SET_SAR_CONFIG"
 - "_NDIS_WWAN_SET_SAR_CONFIG"
ms.keywords: _NDIS_WWAN_SET_SAR_CONFIG, NDIS_WWAN_SET_SAR_CONFIG, *PNDIS_WWAN_SET_SAR_CONFIG, 
req.header: ndiswwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NDIS_WWAN_SET_SAR_CONFIG, *PNDIS_WWAN_SET_SAR_CONFIG
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndiswwan.h
api_name: 
- _NDIS_WWAN_SET_SAR_CONFIG
targetos: Windows
ms.custom: RS5
---

# _NDIS_WWAN_SET_SAR_CONFIG structure

## -description

The **NDIS_WWAN_SET_SAR_CONFIG** structure describes Specific Absorption Rate (SAR) information that a mobile broadband (MB) modem should use to set its SAR configuration.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_SET_SAR_CONFIG** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_SET_SAR_CONFIG_REVISION_1 |
| Size | sizeof(NDIS_WWAN_SET_SAR_CONFIG) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).
 
### -field SetSarConfig
 
A formatted [**WWAN_SET_SAR_CONFIG**](../wwan/ns-wwan-_wwan_set_sar_config.md) structure that describes the SAR information for the modem to set.

## -remarks

This structure is used in an [OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-config) Set request.

After completing the Set request, the modem should return an [NDIS_STATUS_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-sar-config) status notification as a response to inform the OS of the SAR configuration.

## -see-also

[MB SAR Platform Support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-sar-platform-support)

[OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-config)

[NDIS_STATUS_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-sar-config)

[**WWAN_SET_SAR_CONFIG**](../wwan/ns-wwan-_wwan_set_sar_config.md)
