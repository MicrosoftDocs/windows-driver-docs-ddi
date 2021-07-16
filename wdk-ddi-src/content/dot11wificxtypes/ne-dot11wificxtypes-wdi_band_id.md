---
UID: NE:dot11wificxtypes._WDI_BAND_ID
tech.root: netvista
title: WDI_BAND_ID (dot11wificxtypes.h)
ms.date: 06/22/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_BAND_ID enumeration is a UINT32 value that defines a band ID.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
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

### -field WDI_BAND_ID_UNKNOWN

Value = 0

### -field WDI_BAND_ID_2400

2.4 GHz.

Value = 1

### -field WDI_BAND_ID_5000

5 GHz.

Value = 2

### -field WDI_BAND_ID_60000

60 GHz.

Value = 3

### -field WDI_BAND_ID_900

900 GHz.

Value = 4

### -field WDI_BAND_ID_6000

6 GHz.

Value = 6

### -field WDI_BAND_ID_IHV_CUSTOM_START

Specifies the start of the range that is used to define a band ID reported by an IHV.

Value = 0x80000000

### -field WDI_BAND_ID_IHV_CUSTOM_END

Specifies the end of the range that is used to define a band ID reported by an IHV.

Value = 0x81000000

### -field WDI_BAND_ID_ANY

All bands. 

Value = 0xFFFFFFFF

## -remarks

The **WDI_BAND_ID** enum is a value in the [**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-result-parameters) TLV.

## -see-also

[**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-result-parameters)