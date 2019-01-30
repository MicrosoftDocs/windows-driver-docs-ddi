---
UID: NS:ndiswwan._NDIS_WWAN_LTE_ATTACH_CONTEXTS
title: _NDIS_WWAN_LTE_ATTACH_CONTEXTS (ndiswwan.h)
description: The NDIS_WWAN_LTE_ATTACH_CONTEXTS structure describes default LTE attach contexts for the inserted SIM's provider (MCC/MNC pair).
tech.root: netvista
ms.assetid: 103cf958-1c1c-44ff-bc93-ce69bbe43b20
ms.date: 08/22/2018
ms.topic: struct
ms.keywords: _NDIS_WWAN_LTE_ATTACH_CONTEXTS, NDIS_WWAN_LTE_ATTACH_CONTEXTS, *PNDIS_WWAN_LTE_ATTACH_CONTEXTS, 
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
req.typenames: NDIS_WWAN_LTE_ATTACH_CONTEXTS, *PNDIS_WWAN_LTE_ATTACH_CONTEXTS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ndiswwan.h
api_name: 
-	_NDIS_WWAN_LTE_ATTACH_CONTEXTS
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# _NDIS_WWAN_LTE_ATTACH_CONTEXTS structure

## -description

The **NDIS_WWAN_LTE_ATTACH_CONTEXTS** structure describes default LTE attach contexts for the inserted SIM's provider (MCC/MNC pair).

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_LTE_ATTACH_CONTEXTS** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_LTE_ATTACH_CONTEXTS_REVISION_1 |
| Size | sizeof(NDIS_WWAN_LTE_ATTACH_CONTEXTS) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).
 
### -field uStatus

The status of system capability. The following table shows the possible values for this member.

| Value | Meaning |
| --- | --- |
| WWAN_STATUS_SUCCESS | The operation succeeded. |
| WWAN_STATUS_BUSY | The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation. |
| WWAN_STATUS_FAILURE | The operation failed. |
| WWAN_STATUS_NO_DEVICE_SUPPORT | The operation failed because the device does not support this OID. |
 
### -field LteAttachContext
 
A formatted [**WWAN_LTE_ATTACH_CONFIG**](../wwan/ns-wwan-_wwan_lte_attach_config.md) structure that describes the LTE attach contexts for the inserted SIM's provider.

## -remarks

This structure is used in the [NDIS_STATUS_WWAN_LTE_ATTACH_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-lte-attach-config) status notification.

## -see-also

[MB LTE Attach Operations](https://docs.microsoft.com/windows-hardware/drivers/network/mb-lte-attach-operations)

[OID_WWAN_LTE_ATTACH_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-lte-attach-config)

[NDIS_STATUS_WWAN_LTE_ATTACH_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-lte-attach-config)

[**WWAN_LTE_ATTACH_CONFIG**](../wwan/ns-wwan-_wwan_lte_attach_config.md)

[**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md)
