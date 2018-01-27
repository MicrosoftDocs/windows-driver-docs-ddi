---
UID: NE:rilapitypes.RILSUPSERVICEDATAPARAMMASK
title: RILSUPSERVICEDATAPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupservicedataparammask_2.htm
old-project: netvista
ms.assetid: 65901068-d45e-4c3a-b1ee-340427506c7f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_PARAM_SSDI_STATUS, netvista.rilsupservicedataparammask_2, rilapitypes/RIL_PARAM_SSDI_DATA, RIL_PARAM_SSDI_ALL, rilapitypes/RIL_PARAM_SSDI_ALL, RIL_PARAM_SSDI_DATA, RILSUPSERVICEDATAPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_SSDI_VENDOR_ERROR, rilapitypes/RIL_PARAM_SSDI_CC_ERROR, RIL_PARAM_SSDI_SS_ERROR, rilapitypes/RIL_PARAM_SSDI_SS_ERROR, RIL_PARAM_SSDI_CC_ERROR, rilapitypes/RILSUPSERVICEDATAPARAMMASK, rilapitypes/RIL_PARAM_SSDI_VENDOR_ERROR, RIL_PARAM_SSDI_DATASIZE, rilapitypes/RIL_PARAM_SSDI_DATASIZE, RIL_PARAM_SSDI_STATUS, RILSUPSERVICEDATAPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	rilapitypes.h
apiname: 
-	RILSUPSERVICEDATAPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSUPSERVICEDATAPARAMMASK
req.product: Windows 10 or later.
---

# RILSUPSERVICEDATAPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILSUPSERVICEDATAPARAMMASK { 
  RIL_PARAM_SSDI_STATUS,
  RIL_PARAM_SSDI_SS_ERROR,
  RIL_PARAM_SSDI_CC_ERROR,
  RIL_PARAM_SSDI_VENDOR_ERROR,
  RIL_PARAM_SSDI_DATASIZE,
  RIL_PARAM_SSDI_DATA,
  RIL_PARAM_SSDI_ALL
} RILSUPSERVICEDATAPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_SSDI_EXECUTOR



### -field RIL_PARAM_SSDI_STATUS



### -field RIL_PARAM_SSDI_SS_ERROR



### -field RIL_PARAM_SSDI_CC_ERROR



### -field RIL_PARAM_SSDI_VENDOR_ERROR



### -field RIL_PARAM_SSDI_DATASIZE



### -field RIL_PARAM_SSDI_DATA



### -field RIL_PARAM_SSDI_ALL


