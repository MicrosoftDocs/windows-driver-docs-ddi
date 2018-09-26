---
UID: NS:wwan._WWAN_LTE_ATTACH_CONFIG
title: _WWAN_LTE_ATTACH_CONFIG
author: windows-driver-content
description: The WWAN_LTE_ATTACH_CONFIG structure describes default LTE attach contexts for the inserted SIM's provider (MCC/MNC pair).
tech.root: netvista
ms.assetid: 44f9e6c7-0dea-41d6-be9b-73f9945f32a6
ms.author: windowsdriverdev
ms.date: 08/22/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _WWAN_LTE_ATTACH_CONFIG, WWAN_LTE_ATTACH_CONFIG, *PWWAN_LTE_ATTACH_CONFIG, 
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
req.typenames: WWAN_LTE_ATTACH_CONFIG, *PWWAN_LTE_ATTACH_CONFIG
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wwan.h
api_name: 
-	_WWAN_LTE_ATTACH_CONFIG
product: 
- Windows
targetos: Windows
---

# _WWAN_LTE_ATTACH_CONFIG structure

## -description

The **WWAN_LTE_ATTACH_CONFIG** structure describes default LTE attach contexts for the inserted SIM's provider (MCC/MNC pair).

## -struct-fields

### -field ElementCount

A **ULONG** value that specifies the number of contexts in **LteContextArray**.
 
### -field LteContextArray
 
An array of [**WWAN_CONTEXT_V2**](ns-wwan-_wwan_context_v2.md) structures that each represent an LTE attach context.

## -remarks

This structure is used in the [**NDIS_WWAN_LTE_ATTACH_CONTEXTS**](../ndiswwan/ns-ndiswwan-_ndis_wwan_lte_attach_contexts.md) structure.

## -see-also

[MB LTE Attach Operations](https://docs.microsoft.com/windows-hardware/drivers/network/mb-lte-attach-operations)

[**NDIS_WWAN_LTE_ATTACH_CONTEXTS**](../ndiswwan/ns-ndiswwan-_ndis_wwan_lte_attach_contexts.md)

[**WWAN_CONTEXT_V2**](ns-wwan-_wwan_context_v2.md)
