---
UID: NF:wwan.IS_5G_5GC_PRESENT
tech.root: netvista
title: IS_5G_5GC_PRESENT
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: IS_5G_5GC_PRESENT determines whether the device is registered in a 5G SA network.
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
req.target-min-winverclnt: 
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
 - IS_5G_5GC_PRESENT
f1_keywords:
 - IS_5G_5GC_PRESENT
 - wwan/IS_5G_5GC_PRESENT
dev_langs:
 - c++
---

## -description

The **IS_5G_5GC_PRESENT** macro determines whether a mobile broadband (MBB) device is registered in a 5G SA network.

## -parameters

### -param dataClass

A bitmap that represents the data class(es) that the device supports. For a detailed list of values, see the **WwanDataClass** member of [**WWAN_DEVICE_CAPS**](ns-wwan-_wwan_device_caps.md). 5G data service is supported if the WWAN_DATA_CLASS_5G bit is set.

### -param dataSubclass

A bitmap that represents the data subclass(es) that the device supports. The following table shows the possible values for this member.

|Value|Meaning|
|--- |--- |
|WWAN_DATA_SUBCLASS_NONE|There are no subclasses under the accompanying data class.|
|WWAN_DATA_SUBCLASS_5G_ENDC|Evolved Universal Mobile Telecommunications System (UMTS) Terrestrial Radio Access (E-UTRAN) and NR dual connectivity as in 5G Option 3 are supported. Only valid under the WWAN_DATA_CLASS_5G data class.|
|WWAN_DATA_SUBCLASS_5G_NR|Standalone NR as in 5G Option 2 is supported. Only valid under the WWAN_DATA_CLASS_5G data class.|
|WWAN_DATA_SUBCLASS_5G_NEDC|NR and EUTRAN dual connectivity as in 5G Option 4 are supported. Only valid under the WWAN_DATA_CLASS_5G data class.|
|WWAN_DATA_SUBCLASS_5G_ELTE|Standalone eLTE as in 5G option 5 is supported. Only valid under the WWAN_DATA_CLASS_5G data class.|
|WWAN_DATA_SUBCLASS_5G_NGENDC|Next-gen eLTE and NR dual connectivity as in 5G option 7 are supported. Only valid under the WWAN_DATA_CLASS_5G data class.|

## -remarks

## -see-also

[**IS_5GNSA_OPTION3_PRESENT**](nf-wwan-is_5gnsa_option3_present.md)
