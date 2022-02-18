---
UID: NS:ndiswwan._NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
tech.root: netvista
title: NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
ms.date: 01/24/2022
targetos: Windows
description: 
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndiswwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO, *PNDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
 - PNDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
 - NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
f1_keywords:
 - _NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
 - ndiswwan/_NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
 - PNDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
 - ndiswwan/PNDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
 - NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
 - ndiswwan/NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO
---

## -description

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

|Header submember|Value|
|---|---|
|Type|NDIS_OBJECT_TYPE_DEFAULT|
|Revision|NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO_REVISION_1|
|Size|sizeof(NDIS_WWAN_UICC_TERMINAL_CAPABILITY_INFO)|

For more information about these members, see [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header).

### -field uStatus

The status of the operation.

### -field UiccCapabilityInfo

A [**WWAN_UICC_TERMINAL_CAPABILITY_INFO**](../wwan/ns-wwan-wwan_uicc_terminal_capability_info.md) structure. 

## -remarks

## -see-also

[**WWAN_UICC_TERMINAL_CAPABILITY_INFO**](../wwan/ns-wwan-wwan_uicc_terminal_capability_info.md) 