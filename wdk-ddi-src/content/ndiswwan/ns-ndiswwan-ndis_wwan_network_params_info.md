---
UID: NS:ndiswwan._NDIS_WWAN_NETWORK_PARAMS_INFO
tech.root: 
title: NDIS_WWAN_NETWORK_PARAMS_INFO
description: The NDIS_WWAN_NETWORK_PARAMS_INFO structure represents data for NDIS_STATUS_WWAN_NETWORK_PARAMS_STATE notifications.
ms.date: 
targetos: Windows
description: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndiswwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_WWAN_NETWORK_PARAMS_INFO, *PNDIS_WWAN_NETWORK_PARAMS_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_NETWORK_PARAMS_INFO
 - PNDIS_WWAN_NETWORK_PARAMS_INFO
 - NDIS_WWAN_NETWORK_PARAMS_INFO
f1_keywords:
 - _NDIS_WWAN_NETWORK_PARAMS_INFO
 - ndiswwan/_NDIS_WWAN_NETWORK_PARAMS_INFO
 - PNDIS_WWAN_NETWORK_PARAMS_INFO
 - ndiswwan/PNDIS_WWAN_NETWORK_PARAMS_INFO
 - NDIS_WWAN_NETWORK_PARAMS_INFO
 - ndiswwan/NDIS_WWAN_NETWORK_PARAMS_INFO
dev_langs:
 - c++
---

## -description

The **NDIS_WWAN_NETWORK_PARAMS_INFO** structure represents data for NDIS_STATUS_WWAN_NETWORK_PARAMS_STATE notifications.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_NETWORK_PARAMS_INFO** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_NETWORK_PARAMS_INFO_REVISION_1 |
| Size | sizeof(NDIS_WWAN_NETWORK_PARAMS_INFO) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field uStatus

The status of system capability. The following table shows the possible values for this member.

| Value | Meaning |
| --- | --- |
| WWAN_STATUS_SUCCESS | The operation succeeded. |
| WWAN_STATUS_BUSY | The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation. |
| WWAN_STATUS_FAILURE | The operation failed. |
| WWAN_STATUS_NO_DEVICE_SUPPORT | The operation failed because the device does not support this OID. |

### -field NetworkParamsInfo

A formatted [**WWAN_NETWORK_PARAMS_INFO**](../wwan/ns-wwan-wwan_network_params_info.md) structure that describes network parameters.

## -see-also

[**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md)

[**WWAN_NETWORK_PARAMS_INFO**](../wwan/ns-wwan-wwan_network_params_info.md)
