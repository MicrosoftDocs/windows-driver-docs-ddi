---
UID: NS:ndiswwan._NDIS_WWAN_SAR_CONFIG_INFO
title: _NDIS_WWAN_SAR_CONFIG_INFO (ndiswwan.h)
description: The NDIS_WWAN_SAR_CONFIG_INFO structure describes a modem's current Specific Absorption Rate (SAR) configuration information.
tech.root: netvista
ms.assetid: a5a682b3-b08c-4525-a7f2-dec9df51590c
ms.date: 08/20/2018
ms.topic: struct
ms.keywords: _NDIS_WWAN_SAR_CONFIG_INFO, NDIS_WWAN_SAR_CONFIG_INFO, *PNDIS_WWAN_SAR_CONFIG_INFO, 
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
req.typenames: NDIS_WWAN_SAR_CONFIG_INFO, *PNDIS_WWAN_SAR_CONFIG_INFO
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndiswwan.h
api_name: 
- _NDIS_WWAN_SAR_CONFIG_INFO
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _NDIS_WWAN_SAR_CONFIG_INFO structure

## -description

The **NDIS_WWAN_SAR_CONFIG_INFO** structure describes a modem's current Specific Absorption Rate (SAR) configuration information. 

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_SAR_CONFIG_INFO** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_SAR_CONFIG_INFO_REVISION_1 |
| Size | sizeof(NDIS_WWAN_SAR_CONFIG_INFO) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).
 
### -field uStatus

The status of system capability. The following table shows the possible values for this member.

| Value | Meaning |
| --- | --- |
| WWAN_STATUS_SUCCESS | The operation succeeded. |
| WWAN_STATUS_BUSY | The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation. |
| WWAN_STATUS_FAILURE | The operation failed. |
| WWAN_STATUS_NO_DEVICE_SUPPORT | The operation failed because the device does not support this OID. |
 
### -field SarConfig

A formatted [**WWAN_SAR_CONFIG_INFO**](../wwan/ns-wwan-_wwan_sar_config_info.md) structure that describes the current SAR configuration information.

## -remarks

This structure is used in the [NDIS_STATUS_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-sar-config) status notification in response to a previous [OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-config) Query or Set request.

## -see-also

[MB SAR Platform Support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-sar-platform-support)

[OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-config)

[NDIS_STATUS_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-sar-config)

[**WWAN_SAR_CONFIG_INFO**](../wwan/ns-wwan-_wwan_sar_config_info.md)
