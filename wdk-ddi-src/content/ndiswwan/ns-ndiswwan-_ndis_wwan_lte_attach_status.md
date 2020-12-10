---
UID: NS:ndiswwan._NDIS_WWAN_LTE_ATTACH_STATUS
title: _NDIS_WWAN_LTE_ATTACH_STATUS (ndiswwan.h)
description: The NDIS_WWAN_LTE_ATTACH_STATUS structure describes the last used default LTE attach context for a mobile broadband (MBB) modem.
tech.root: netvista
ms.date: 08/23/2018
keywords: ["NDIS_WWAN_LTE_ATTACH_STATUS structure"]
ms.keywords: _NDIS_WWAN_LTE_ATTACH_STATUS, NDIS_WWAN_LTE_ATTACH_STATUS, *PNDIS_WWAN_LTE_ATTACH_STATUS,
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
req.typenames: NDIS_WWAN_LTE_ATTACH_STATUS, *PNDIS_WWAN_LTE_ATTACH_STATUS
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NDIS_WWAN_LTE_ATTACH_STATUS
 - ndiswwan/_NDIS_WWAN_LTE_ATTACH_STATUS
 - PNDIS_WWAN_LTE_ATTACH_STATUS
 - ndiswwan/PNDIS_WWAN_LTE_ATTACH_STATUS
 - NDIS_WWAN_LTE_ATTACH_STATUS
 - ndiswwan/NDIS_WWAN_LTE_ATTACH_STATUS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_LTE_ATTACH_STATUS
product:
 - Windows
---

# _NDIS_WWAN_LTE_ATTACH_STATUS structure


## -description

The **NDIS_WWAN_LTE_ATTACH_STATUS** structure describes the last used default LTE attach context for a mobile broadband (MBB) modem.

## -struct-fields

### -field Header

 
The header with type, revision, and size information about the **NDIS_WWAN_LTE_ATTACH_STATUS** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_LTE_ATTACH_STATUS_REVISION_1 |
| Size | sizeof(NDIS_WWAN_LTE_ATTACH_STATUS) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field uStatus

The status of system capability. The following table shows the possible values for this member.

| Value | Meaning |
| --- | --- |
| WWAN_STATUS_SUCCESS | The operation succeeded. |
| WWAN_STATUS_BUSY | The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation. |
| WWAN_STATUS_FAILURE | The operation failed. |
| WWAN_STATUS_NO_DEVICE_SUPPORT | The operation failed because the device does not support this OID. |

### -field LteAttachStatus

A formatted [**WWAN_LTE_ATTACH_STATUS**](../wwan/ns-wwan-_wwan_lte_attach_status.md) structure that describes the last used default LTE attach context for the modem.

## -remarks

This structure is used in the [NDIS_STATUS_WWAN_LTE_ATTACH_STATUS](/windows-hardware/drivers/network/ndis-status-wwan-lte-attach-status) status notification.

## -see-also

[MB LTE Attach Operations](/windows-hardware/drivers/network/mb-lte-attach-operations)

[OID_WWAN_LTE_ATTACH_STATUS](/windows-hardware/drivers/network/oid-wwan-lte-attach-status)

[NDIS_STATUS_WWAN_LTE_ATTACH_STATUS](/windows-hardware/drivers/network/ndis-status-wwan-lte-attach-status)

[**WWAN_LTE_ATTACH_STATUS**](../wwan/ns-wwan-_wwan_lte_attach_status.md)

[**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md)
