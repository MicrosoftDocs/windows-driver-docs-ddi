---
UID: NE:dot11wificxtypes._WDI_BAND_ID
tech.root: netvista
<<<<<<< HEAD
title: WDI_BAND_ID (dot11wificxtypes.h)
ms.date: 06/22/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_BAND_ID enumeration is a UINT32 value that defines a band ID.
=======
title: WDI_BAND_ID
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WDI_BAND_ID enumeration for internal use only. Don't use this enumeration in your code."
>>>>>>> main
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11Windows 11
>>>>>>> main
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_BAND_ID
 - WDI_BAND_ID
f1_keywords:
 - _WDI_BAND_ID
 - dot11wificxtypes/_WDI_BAND_ID
 - WDI_BAND_ID
 - dot11wificxtypes/WDI_BAND_ID
dev_langs:
 - c++
---

## -description

The **WDI_BAND_ID** enumeration is a UINT32 value that defines a band ID.

## -enum-fields

### -field WDI_BAND_ID_UNKNOWN:0

The band ID is unknown.

### -field WDI_BAND_ID_2400:1

2.4 GHz.

### -field WDI_BAND_ID_5000:2

5 GHz.

### -field WDI_BAND_ID_60000:3

60 GHz.

### -field WDI_BAND_ID_900:4

900 GHz.

### -field WDI_BAND_ID_6000:6

6 GHz.

### -field WDI_BAND_ID_IHV_CUSTOM_START:0x80000000

Specifies the start of the range that is used to define a band ID reported by an IHV.

### -field WDI_BAND_ID_IHV_CUSTOM_END:0x81000000

Specifies the end of the range that is used to define a band ID reported by an IHV.

### -field WDI_BAND_ID_ANY:0xFFFFFFFF

All bands. 

## -remarks

The **WDI_BAND_ID** enum is a value in the [**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-result-parameters) TLV.

## -see-also

[**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-result-parameters)