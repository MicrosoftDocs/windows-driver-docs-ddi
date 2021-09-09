---
UID: NE:dot11wificxtypes._WDI_DS_INFO
tech.root: netvista
<<<<<<< HEAD
title: WDI_DS_INFO (dot11wificxtypes.h)
ms.date: 06/30/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_DS_INFO enum defines values that specify whether the port is connected to the same DS that it was previously associated to.
=======
title: WDI_DS_INFO
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WDI_DS_INFO enumeration for internal use only. Don't use this enumeration in your code."
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
 - _WDI_DS_INFO
 - WDI_DS_INFO
f1_keywords:
 - _WDI_DS_INFO
 - dot11wificxtypes/_WDI_DS_INFO
 - WDI_DS_INFO
 - dot11wificxtypes/WDI_DS_INFO
dev_langs:
 - c++
---

## -description

The **WDI_DS_INFO** enumeration defines values that specify whether the port is connected to the same DS that it was previously associated to.

## -enum-fields

### -field WDI_DS_CHANGED

New DS.

### -field WDI_DS_UNCHANGED

Same DS as previously associated.

### -field WDI_DS_UNKNOWN

Unable to determine if the DS has changed.

### -field WDI_DS_MAX



## -remarks

The **WDI_AUTH_ALGORITHM** enum is a value in the [**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-result-parameters) TLV.

## -see-also

[**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-result-parameters)
