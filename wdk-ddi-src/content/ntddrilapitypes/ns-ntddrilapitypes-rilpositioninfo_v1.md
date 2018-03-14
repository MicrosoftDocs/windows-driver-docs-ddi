---
UID: NS:ntddrilapitypes.RILPOSITIONINFO_V1
title: RILPOSITIONINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfo_v1_2.htm
old-project: netvista
ms.assetid: ff622111-e4c3-47eb-9509-dbe86d0d5acf
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILPOSITIONINFO_V1, RILPOSITIONINFO_V1, RILPOSITIONINFO_V1 structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfo_v1_2, ntddrilapitypes/RILPOSITIONINFO_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILPOSITIONINFO_V1
product: Windows
targetos: Windows
req.typenames: RILPOSITIONINFO_V1, *LPRILPOSITIONINFO_V1
---

# RILPOSITIONINFO_V1 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILPOSITIONINFO_V1 {
  DWORD                                   cbSize;
  DWORD                                   dwSystemType;
  RILPOSITIONINFOGSM                      stGSMServingCellInfo;
  RILPOSITIONINFOUMTS                     stUMTSServingCellInfo;
  RILPOSITIONINFOLTE                      stLTEServingCellInfo;
  DWORD                                   dwCntGSMNMR;
  RILGSMNMR [MAX_GSMPOS_COUNT_OF_NMR]     rgNMR;
  DWORD                                   dwCntUMTSMRL;
  RILUMTSMRL [MAX_UMTSPOS_COUNT_OF_MRL]   ruMRL;
  DWORD                                   dwCntEUTRAMRL;
  RILEUTRAMRL [MAX_EUTRAPOS_COUNT_OF_MRL] reMRL;
  DWORD                                   dwCntC2KMRL;
  RILC2KMRL [MAX_C2KPOS_COUNT_OF_MRL]     rc2kMRL;
} RILPOSITIONINFO_V1, RILPOSITIONINFO_V1;
````


## -struct-fields




### -field cbSize


### -field dwSystemType


### -field stGSMServingCellInfo


### -field stUMTSServingCellInfo


### -field stLTEServingCellInfo


### -field dwCntGSMNMR


### -field rgNMR


### -field dwCntUMTSMRL


### -field ruMRL


### -field dwCntEUTRAMRL


### -field reMRL


### -field dwCntC2KMRL


### -field rc2kMRL

