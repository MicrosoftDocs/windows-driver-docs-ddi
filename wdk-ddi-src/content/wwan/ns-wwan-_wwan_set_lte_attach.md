---
UID: NS:wwan._WWAN_SET_LTE_ATTACH
title: _WWAN_SET_LTE_ATTACH (wwan.h)
description: The WWAN_SET_LTE_ATTACH structure describes default LTE attach contexts a miniport driver should set for the inserted SIM's provider (MCC/MNC pair).
tech.root: netvista
ms.assetid: 33071437-8d4f-45d8-ba61-66ab9776a9e8
ms.date: 08/22/2018
keywords: ["_WWAN_SET_LTE_ATTACH structure"]
f1_keywords:
 - "wwan/_WWAN_SET_LTE_ATTACH"
ms.keywords: _WWAN_SET_LTE_ATTACH, WWAN_SET_LTE_ATTACH, *PWWAN_SET_LTE_ATTACH, 
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
req.typenames: WWAN_SET_LTE_ATTACH, *PWWAN_SET_LTE_ATTACH
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_SET_LTE_ATTACH
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_SET_LTE_ATTACH structure

## -description

The **WWAN_SET_LTE_ATTACH** structure describes default LTE attach contexts a miniport driver should set for the inserted SIM's provider (MCC/MNC pair).

## -struct-fields

### -field SetContextArray
 
An array of [**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md) structures that each represent an LTE attach context to set.

## -remarks

This structure is used in the [**NDIS_WWAN_SET_LTE_ATTACH_CONTEXT**](../ndiswwan/ns-ndiswwan-_ndis_wwan_set_lte_attach_context.md) structure, which is used in the payload of an [OID_WWAN_LTE_ATTACH_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-lte-attach-config) Set request. If this structure does not contain exactly three contexts, one each for home, partner, and non-partner roaming conditions, the miniport driver should reject the request.

## -see-also

[MB LTE Attach Operations](https://docs.microsoft.com/windows-hardware/drivers/network/mb-lte-attach-operations)

[**NDIS_WWAN_SET_LTE_ATTACH_CONTEXT**](../ndiswwan/ns-ndiswwan-_ndis_wwan_set_lte_attach_context.md)

[**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md)
