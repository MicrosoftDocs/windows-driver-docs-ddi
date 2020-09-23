---
UID: NS:wwan._WWAN_LTE_ATTACH_STATUS
title: _WWAN_LTE_ATTACH_STATUS (wwan.h)
description: The WWAN_LTE_ATTACH_STATUS structure describes the last used default LTE attach context for a mobile broadband (MBB) modem.
tech.root: netvista
ms.assetid: f8e43c3a-d22c-4bb6-bf50-bb98a776deae
ms.date: 08/23/2018
keywords: ["WWAN_LTE_ATTACH_STATUS structure"]
ms.keywords: _WWAN_LTE_ATTACH_STATUS, WWAN_LTE_ATTACH_STATUS, *PWWAN_LTE_ATTACH_STATUS,
req.header: wwan.h
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
req.typenames: WWAN_LTE_ATTACH_STATUS, *PWWAN_LTE_ATTACH_STATUS
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _WWAN_LTE_ATTACH_STATUS
 - wwan/_WWAN_LTE_ATTACH_STATUS
 - PWWAN_LTE_ATTACH_STATUS
 - wwan/PWWAN_LTE_ATTACH_STATUS
 - WWAN_LTE_ATTACH_STATUS
 - wwan/WWAN_LTE_ATTACH_STATUS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_LTE_ATTACH_STATUS
product:
 - Windows
---

# _WWAN_LTE_ATTACH_STATUS structure


## -description

The **WWAN_LTE_ATTACH_STATUS** structure describes the last used default LTE attach context for a mobile broadband (MBB) modem.

## -struct-fields

### -field LteAttachState

A [**WWAN_CONTEXT_LTE_ATTACH_STATE**](ne-wwan-_wwan_context_lte_attach_state.md) value that indicates whether the device is currently attach to an LTE network or not.

### -field IPType

A [**WWAN_IP_TYPE**](ne-wwan-_wwan_ip_type.md) value that specifies the supported IP types for the default LTE attach context.

### -field basicInfo

A [**WWAN_CONTEXT**](ns-wwan-_wwan_context.md) structure that represents the basic information for the default LTE attach context.

## -remarks

This structure is used in the [**NDIS_WWAN_LTE_ATTACH_STATUS**](../ndiswwan/ns-ndiswwan-_ndis_wwan_lte_attach_status.md) structure.

## -see-also

[MB LTE Attach Operations](/windows-hardware/drivers/network/mb-lte-attach-operations)

[**NDIS_WWAN_LTE_ATTACH_STATUS**](../ndiswwan/ns-ndiswwan-_ndis_wwan_lte_attach_status.md)