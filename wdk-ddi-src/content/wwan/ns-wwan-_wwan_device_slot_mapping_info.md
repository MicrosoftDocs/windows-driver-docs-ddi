---
UID: NS:wwan._WWAN_DEVICE_SLOT_MAPPING_INFO
title: _WWAN_DEVICE_SLOT_MAPPING_INFO (wwan.h)
description: The WWAN_DEVICE_SLOT_MAPPING_INFO structure represents the executor-to-slot mapping relationship in the MB device.
old-location: netvista\wwan_device_slot_mappings.htm
tech.root: netvista
ms.assetid: 48DD867C-1235-4955-A01E-FF46C850DA31
ms.date: 05/02/2018
keywords: ["WWAN_DEVICE_SLOT_MAPPING_INFO structure"]
ms.keywords: "*PWWAN_DEVICE_SLOT_MAPPING_INFO, PWWAN_DEVICE_SLOT_MAPPING_INFO, PWWAN_DEVICE_SLOT_MAPPING_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SLOT_MAPPING_INFO, WWAN_DEVICE_SLOT_MAPPING_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SLOT_MAPPING_INFO, netvista.wwan_device_slot_mappings, wwan/PWWAN_DEVICE_SLOT_MAPPING_INFO, wwan/WWAN_DEVICE_SLOT_MAPPING_INFO"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WWAN_DEVICE_SLOT_MAPPING_INFO, *PWWAN_DEVICE_SLOT_MAPPING_INFO
f1_keywords:
 - _WWAN_DEVICE_SLOT_MAPPING_INFO
 - wwan/_WWAN_DEVICE_SLOT_MAPPING_INFO
 - PWWAN_DEVICE_SLOT_MAPPING_INFO
 - wwan/PWWAN_DEVICE_SLOT_MAPPING_INFO
 - WWAN_DEVICE_SLOT_MAPPING_INFO
 - wwan/WWAN_DEVICE_SLOT_MAPPING_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_DEVICE_SLOT_MAPPING_INFO
---

# _WWAN_DEVICE_SLOT_MAPPING_INFO structure


## -description

The WWAN_DEVICE_SLOT_MAPPING_INFO structure represents the executor-to-slot mapping relationship in the MB device.

## -struct-fields

### -field SlotMapListHeader

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_list_header">WWAN_LIST_HEADER</a> has a new structure, <b>WwanStructSlotIndex</b>, which represents the slot index the <i>i-th</i> executor is mapped to (where 0 <= i <= (Number of mappings -1)).

## -see-also

<a href="/windows-hardware/drivers/network/ndis-status-wwan-device-slot-mappings">NDIS_STATUS_WWAN_DEVICE_SLOT_MAPPING_INFO</a>



<a href="/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_device_slot_mapping_info">NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO</a>



<a href="/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_set_device_slot_mapping_info">NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO</a>



<a href="/windows-hardware/drivers/network/oid-wwan-device-slot-mappings">OID_WWAN_DEVICE_SLOT_MAPPING_INFO</a>