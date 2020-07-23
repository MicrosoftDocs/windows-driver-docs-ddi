---
UID: NS:ndiswwan._NDIS_WWAN_PIN_APP
title: _NDIS_WWAN_PIN_APP (ndiswwan.h)
description: The NDIS_WWAN_PIN_APP structure specifies the target application ID for a UICC application whose PIN is being queried. 
tech.root: netvista
ms.assetid: 9E401F36-21E5-482D-A8A6-952046911E20
ms.date: 04/10/2019
keywords: ["_NDIS_WWAN_PIN_APP structure"]
f1_keywords:
 - "ndiswwan/_NDIS_WWAN_PIN_APP"
 - "_NDIS_WWAN_PIN_APP"
ms.keywords: _NDIS_WWAN_PIN_APP, NDIS_WWAN_PIN_APP, *PNDIS_WWAN_PIN_APP, 
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
req.typenames: NDIS_WWAN_PIN_APP, *PNDIS_WWAN_PIN_APP
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndiswwan.h
api_name: 
- _NDIS_WWAN_PIN_APP
targetos: Windows
ms.custom: 19H1
---

# _NDIS_WWAN_PIN_APP structure

## -description

The **NDIS_WWAN_PIN_APP** structure specifies the target application ID for a UICC application whose PIN is being queried. 

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_PIN_APP** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_PIN_APP_REVISION_1 |
| Size | sizeof(NDIS_WWAN_PIN_APP) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).
 
### -field PinApp

A formatted [**WWAN_PIN_APP**](../wwan/ns-wwan-_wwan_pin_app.md) structure that describes the application ID.

## -remarks

This structure is used in the payload of an [OID_WWAN_PIN_EX2](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-pin-ex2) Query request.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_PIN_EX2](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-pin-ex2)

[**WWAN_PIN_APP**](../wwan/ns-wwan-_wwan_pin_app.md)
