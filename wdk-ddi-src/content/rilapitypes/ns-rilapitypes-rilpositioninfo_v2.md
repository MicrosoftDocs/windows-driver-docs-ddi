---
UID: NS:rilapitypes.RILPOSITIONINFO_V2
title: RILPOSITIONINFO_V2 (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfo_v2_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILPOSITIONINFO_V2 structure"]
ms.keywords: "*LPRILPOSITIONINFO, *LPRILPOSITIONINFO_V2, RILPOSITIONINFO, RILPOSITIONINFO_V2, RILPOSITIONINFO_V2 structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfo_v2_2, rilapitypes/RILPOSITIONINFO_V2"
req.header: rilapitypes.h
req.include-header: 
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
req.typenames: RILPOSITIONINFO_V2, *LPRILPOSITIONINFO_V2, RILPOSITIONINFO, *LPRILPOSITIONINFO
req.product: Windows 10 or later.
f1_keywords:
 - RILPOSITIONINFO_V2
 - rilapitypes/RILPOSITIONINFO_V2
 - LPRILPOSITIONINFO_V2
 - rilapitypes/LPRILPOSITIONINFO_V2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILPOSITIONINFO_V2
 - LPRILPOSITIONINFO_V2
---

# RILPOSITIONINFO_V2 structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field cbSize

### -field dwSystemType

### -field stGSMServingCellInfo

### -field stUMTSServingCellInfo

### -field stTDSCDMAServingCellInfo

### -field stLTEServingCellInfo

### -field dwCntGSMNMR

### -field rgNMR

### -field dwCntUMTSMRL

### -field ruMRL

### -field dwCntTDSCDMAMRL

### -field rtMRL

### -field dwCntEUTRAMRL

### -field reMRL

### -field dwCntC2KMRL

### -field rc2kMRL

## -syntax

```cpp
typedef struct _RILPOSITIONINFO_V2 {
  DWORD                                       cbSize;
  DWORD                                       dwSystemType;
  RILPOSITIONINFOGSM                          stGSMServingCellInfo;
  RILPOSITIONINFOUMTS                         stUMTSServingCellInfo;
  RILPOSITIONINFOTDSCDMA                      stTDSCDMAServingCellInfo;
  RILPOSITIONINFOLTE                          stLTEServingCellInfo;
  DWORD                                       dwCntGSMNMR;
  RILGSMNMR [MAX_GSMPOS_COUNT_OF_NMR]         rgNMR;
  DWORD                                       dwCntUMTSMRL;
  RILUMTSMRL [MAX_UMTSPOS_COUNT_OF_MRL]       ruMRL;
  DWORD                                       dwCntTDSCDMAMRL;
  RILTDSCDMAMRL [MAX_TDSCDMAPOS_COUNT_OF_MRL] rtMRL;
  DWORD                                       dwCntEUTRAMRL;
  RILEUTRAMRL [MAX_EUTRAPOS_COUNT_OF_MRL]     reMRL;
  DWORD                                       dwCntC2KMRL;
  RILC2KMRL [MAX_C2KPOS_COUNT_OF_MRL]         rc2kMRL;
} RILPOSITIONINFO_V2, RILPOSITIONINFO_V2;
```

