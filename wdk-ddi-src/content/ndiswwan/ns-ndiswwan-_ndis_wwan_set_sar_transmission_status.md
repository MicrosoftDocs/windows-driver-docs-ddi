---
UID: NS:ndiswwan._NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS
title: _NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS (ndiswwan.h)
description: The NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS structure sets Specific Absorption Rate (SAR) transmission status in a mobile broadband (MBB) modem.
tech.root: netvista
ms.date: 08/20/2018
keywords: ["NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS structure"]
ms.keywords: _NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS, NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS, *PNDIS_WWAN_SET_SAR_TRANSMISSION_STATUS,
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
req.typenames: NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS, *PNDIS_WWAN_SET_SAR_TRANSMISSION_STATUS
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS
 - ndiswwan/_NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS
 - PNDIS_WWAN_SET_SAR_TRANSMISSION_STATUS
 - ndiswwan/PNDIS_WWAN_SET_SAR_TRANSMISSION_STATUS
 - NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS
 - ndiswwan/NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS
 - PNDIS_WWAN_SET_SAR_TRANSMISSION_STATUS
 - NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS
---

# _NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS structure


## -description

The **NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS** structure sets Specific Absorption Rate (SAR) transmission status in a mobile broadband (MBB) modem.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS_REVISION_1 |
| Size | sizeof(NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field SetTransmissionStatus

A formatted [**WWAN_SET_SAR_TRANSMISSION_STATUS**](../wwan/ns-wwan-_wwan_set_sar_transmission_status.md) structure that specifies the SAR transmission status to be set in the modem.

## -remarks

This structure is used in an [OID_WWAN_SAR_TRANSMISSION_STATUS](/windows-hardware/drivers/network/oid-wwan-sar-transmission-status) Set request.

## -see-also

[MB SAR Platform Support](/windows-hardware/drivers/network/mb-sar-platform-support)

[OID_WWAN_SAR_TRANSMISSION_STATUS](/windows-hardware/drivers/network/oid-wwan-sar-transmission-status)

[NDIS_STATUS_WWAN_SAR_TRANSMISSION_STATUS](/windows-hardware/drivers/network/ndis-status-wwan-sar-transmission-status)

[**WWAN_SET_SAR_TRANSMISSION_STATUS**](../wwan/ns-wwan-_wwan_set_sar_transmission_status.md)

