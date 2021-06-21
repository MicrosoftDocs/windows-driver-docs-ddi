---
UID: NF:wwan.IS_5GNSA_OPTION3_PRESENT
tech.root: netvista
title: IS_5GNSA_OPTION3_PRESENT
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: IS_5GNSA_OPTION3_PRESENT determines whether an MBB device is registered in a 5G NSA (Option 3) network.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN10_NEXT
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - IS_5GNSA_OPTION3_PRESENT
f1_keywords:
 - IS_5GNSA_OPTION3_PRESENT
 - wwan/IS_5GNSA_OPTION3_PRESENT
dev_langs:
 - c++
---

## -description

The **IS_5GNSA_OPTION3_PRESENT** macro determines whether a mobile broadband (MBB) device is registered in a 5G NSA (Option 3) network.

## -parameters

### -param dataClass

A bitmap that represents the data class(es) that the device supports. For a detailed list of values, see the **WwanDataClass** member of [**WWAN_DEVICE_CAPS**](ns-wwan-_wwan_device_caps.md). The WWAN_DATA_CLASS_5G bit must be set if 5G NSA data service is supported. 

### -param dataSubclass

A bitmap that represents the data subclass(es) that the device supports. For a detailed list of values, see the **dataSubclass** member of [**IS_5G_5GC_PRESENT**](nf-wwan-is_5g_5gc_present.md). 5G NSA data service is supported if the WWAN_DATA_SUBCLASS_5G_ENDC bit is set.

## -remarks

## -see-also

[**IS_5G_5GC_PRESENT**](nf-wwan-is_5g_5gc_present.md)