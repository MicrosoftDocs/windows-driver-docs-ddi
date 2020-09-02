---
UID: NE:ntddrilapitypes.RILUICCFILELOCKSTATUSACCESSCONDITION
title: RILUICCFILELOCKSTATUSACCESSCONDITION (ntddrilapitypes.h)
description: This enumeration describes the RILUICCFILELOCKSTATUSACCESSCONDITION.
old-location: netvista\riluiccfilelockstatusaccesscondition.htm
tech.root: netvista
ms.assetid: 994bfab2-6bab-4aeb-87a9-a5b825efcb23
ms.date: 02/16/2018
keywords: ["RILUICCFILELOCKSTATUSACCESSCONDITION enumeration"]
ms.keywords: RILUICCFILELOCKSTATUSACCESSCONDITION, RILUICCFILELOCKSTATUSACCESSCONDITION enumeration [Network Drivers Starting with Windows Vista], RIL_UICCFILEACCESSCONDITION_ADM5, RIL_UICCFILEACCESSCONDITION_ADM6, RIL_UICCFILEACCESSCONDITION_ALW, RIL_UICCFILEACCESSCONDITION_NEV, RIL_UICCFILEACCESSCONDITION_PIN1, RIL_UICCFILEACCESSCONDITION_PIN2, RIL_UICCFILEACCESSCONDITION_RFU3, RIL_UICCFILEACCESSCONDITION_RFU4, netvista.riluiccfilelockstatusaccesscondition, rilapitypes/RILUICCFILELOCKSTATUSACCESSCONDITION, rilapitypes/RIL_UICCFILEACCESSCONDITION_ADM5, rilapitypes/RIL_UICCFILEACCESSCONDITION_ADM6, rilapitypes/RIL_UICCFILEACCESSCONDITION_ALW, rilapitypes/RIL_UICCFILEACCESSCONDITION_NEV, rilapitypes/RIL_UICCFILEACCESSCONDITION_PIN1, rilapitypes/RIL_UICCFILEACCESSCONDITION_PIN2, rilapitypes/RIL_UICCFILEACCESSCONDITION_RFU3, rilapitypes/RIL_UICCFILEACCESSCONDITION_RFU4
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: RILUICCFILELOCKSTATUSACCESSCONDITION
f1_keywords:
 - RILUICCFILELOCKSTATUSACCESSCONDITION
 - ntddrilapitypes/RILUICCFILELOCKSTATUSACCESSCONDITION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUICCFILELOCKSTATUSACCESSCONDITION
---

# RILUICCFILELOCKSTATUSACCESSCONDITION enumeration


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCFILELOCKSTATUSACCESSCONDITION.

## -enum-fields

### -field RIL_UICCFILEACCESSCONDITION_ALW

### -field RIL_UICCFILEACCESSCONDITION_PIN1

### -field RIL_UICCFILEACCESSCONDITION_PIN2

### -field RIL_UICCFILEACCESSCONDITION_RFU3

### -field RIL_UICCFILEACCESSCONDITION_RFU4

### -field RIL_UICCFILEACCESSCONDITION_ADM5

### -field RIL_UICCFILEACCESSCONDITION_ADM6

### -field RIL_UICCFILEACCESSCONDITION_NEV

### -field RIL_UICCFILEACCESSCONDITION_MAX

## -syntax

```cpp
enum RILUICCFILELOCKSTATUSACCESSCONDITION {
  RIL_UICCFILEACCESSCONDITION_ALW   = 0x00,
  RIL_UICCFILEACCESSCONDITION_PIN1  = 0x01,
  RIL_UICCFILEACCESSCONDITION_PIN2  = 0x02,
  RIL_UICCFILEACCESSCONDITION_RFU3  = 0x03,
  RIL_UICCFILEACCESSCONDITION_RFU4  = 0x04,
  RIL_UICCFILEACCESSCONDITION_ADM5  = 0x05,
  RIL_UICCFILEACCESSCONDITION_ADM6  = 0x06,
  RIL_UICCFILEACCESSCONDITION_NEV   = 0x07

};
```

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>

