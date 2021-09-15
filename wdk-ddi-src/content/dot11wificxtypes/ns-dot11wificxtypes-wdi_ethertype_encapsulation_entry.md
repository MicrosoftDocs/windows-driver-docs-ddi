---
UID: NS:dot11wificxtypes._WDI_ETHERTYPE_ENCAPSULATION_ENTRY
tech.root: netvista
title: WDI_ETHERTYPE_ENCAPSULATION_ENTRY (dot11wificxtypes.h)
ms.date: 09/15/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_ETHERTYPE_ENCAPSULATION_ENTRY struct defines an EtherType encapsulation entry.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WDI_ETHERTYPE_ENCAPSULATION_ENTRY, *PWDI_ETHERTYPE_ENCAPSULATION_ENTRY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - PWDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - WDI_ETHERTYPE_ENCAPSULATION_ENTRY
f1_keywords:
 - _WDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - dot11wificxtypes/_WDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - PWDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - dot11wificxtypes/PWDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - WDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - dot11wificxtypes/WDI_ETHERTYPE_ENCAPSULATION_ENTRY
dev_langs:
 - c++
---

## -description

The **WDI_ETHERTYPE_ENCAPSULATION_ENTRY** structure defines an EtherType encapsulation entry.

## -struct-fields

### -field EtherType

The value of the IEEE EtherType in big-endian byte order.

### -field EncapsulationType

The type of encapsulation to be performed on the specified EtherType.

## -remarks

The **WDI_ETHERTYPE_ENCAPSULATION_ENTRY** structure is a value in the [**WDI_TLV_ETHERTYPE_ENCAP_TABLE**](/windows-hardware/drivers/netcx/wdi-tlv-ethertype-encap-table) TLV.


## -see-also

[**WDI_TLV_ETHERTYPE_ENCAP_TABLE**](/windows-hardware/drivers/netcx/wdi-tlv-ethertype-encap-table)