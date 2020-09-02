---
UID: NS:ndiswwan._NDIS_WWAN_NITZ_INFO
title: _NDIS_WWAN_NITZ_INFO (ndiswwan.h)
description: The NDIS_WWAN_NITZ_INFO structure describes the current network time and time zone information.
tech.root: netvista
ms.assetid: 71072272-67C1-4B17-AAE2-66F808472D83
ms.date: 04/11/2019
keywords: ["NDIS_WWAN_NITZ_INFO structure"]
ms.keywords: _NDIS_WWAN_NITZ_INFO, NDIS_WWAN_NITZ_INFO, *PNDIS_WWAN_NITZ_INFO,
req.header: ndiswwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NDIS_WWAN_NITZ_INFO, *PNDIS_WWAN_NITZ_INFO
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _NDIS_WWAN_NITZ_INFO
 - ndiswwan/_NDIS_WWAN_NITZ_INFO
 - PNDIS_WWAN_NITZ_INFO
 - ndiswwan/PNDIS_WWAN_NITZ_INFO
 - NDIS_WWAN_NITZ_INFO
 - ndiswwan/NDIS_WWAN_NITZ_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_NITZ_INFO
---

# _NDIS_WWAN_NITZ_INFO structure


## -description

The **NDIS_WWAN_NITZ_INFO** structure describes the current network time and time zone information.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_NITZ_INFO** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_NITZ_INFO_REVISION_1 |
| Size | sizeof(NDIS_WWAN_NITZ_INFO) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field uStatus

The status of system capability. The following table shows the possible values for this member.

| Value | Meaning |
| --- | --- |
| WWAN_STATUS_SUCCESS | The operation succeeded. |
| WWAN_STATUS_BUSY | The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation. |
| WWAN_STATUS_FAILURE | The operation failed. |
| WWAN_STATUS_NO_DEVICE_SUPPORT | The operation failed because the device does not support this OID. |

### -field NitzInfo

A formatted [**WWAN_NITZ_INFO**](../wwan/ns-wwan-_wwan_nitz_info.md) structure that describes the current network time and time zone information.

## -remarks

This structure is used in the [NDIS_STATUS_WWAN_NITZ_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-nitz-info) status notification either in response to a previous [OID_WWAN_NITZ](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-nitz) Query request, or as an unsolicited notification.

## -see-also

[MB NITZ support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-nitz-support)

[OID_WWAN_NITZ](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-nitz)

[NDIS_STATUS_WWAN_NITZ_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-nitz-info)

[**WWAN_NITZ_INFO**](../wwan/ns-wwan-_wwan_nitz_info.md)

