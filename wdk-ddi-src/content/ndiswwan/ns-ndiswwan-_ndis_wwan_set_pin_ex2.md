---
UID: NS:ndiswwan._NDIS_WWAN_SET_PIN_EX2
title: _NDIS_WWAN_SET_PIN_EX2 (ndiswwan.h)
description: The NDIS_WWAN_SET_PIN_EX2 structure specifies the PIN action to take for a UICC application.
tech.root: netvista
ms.assetid: E4AAF4D1-687A-48DA-AE6F-0C7ABEAFD02E
ms.date: 04/10/2019
keywords: ["NDIS_WWAN_SET_PIN_EX2 structure"]
ms.keywords: _NDIS_WWAN_SET_PIN_EX2, NDIS_WWAN_SET_PIN_EX2, *PNDIS_WWAN_SET_PIN_EX2,
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
req.typenames: NDIS_WWAN_SET_PIN_EX2, *PNDIS_WWAN_SET_PIN_EX2
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _NDIS_WWAN_SET_PIN_EX2
 - ndiswwan/_NDIS_WWAN_SET_PIN_EX2
 - PNDIS_WWAN_SET_PIN_EX2
 - ndiswwan/PNDIS_WWAN_SET_PIN_EX2
 - NDIS_WWAN_SET_PIN_EX2
 - ndiswwan/NDIS_WWAN_SET_PIN_EX2
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_SET_PIN_EX2
---

# _NDIS_WWAN_SET_PIN_EX2 structure


## -description

The **NDIS_WWAN_SET_PIN_EX2** structure specifies the PIN action to take for a UICC application.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_SET_PIN_EX2** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_SET_PIN_EX2_REVISION_1 |
| Size | sizeof(NDIS_WWAN_SET_PIN_EX2) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field PinApp

A formatted [**WWAN_PIN_ACTION_EX2**](../wwan/ns-wwan-_wwan_pin_action_ex2.md) structure that describes the PIN action.

## -remarks

This structure is used in the payload of an [OID_WWAN_PIN_EX2](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-pin-ex2) Set request.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_PIN_EX2](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-pin-ex2)

[**WWAN_PIN_ACTION_EX2**](../wwan/ns-wwan-_wwan_pin_action_ex2.md)

