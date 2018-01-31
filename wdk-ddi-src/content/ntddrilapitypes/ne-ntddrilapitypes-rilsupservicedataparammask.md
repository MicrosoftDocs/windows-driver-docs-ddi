---
UID: NE:ntddrilapitypes.RILSUPSERVICEDATAPARAMMASK
title: RILSUPSERVICEDATAPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupservicedataparammask.htm
old-project: netvista
ms.assetid: 2b0ff5a7-02b3-4a22-98da-d13825bc2f45
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_PARAM_SSDI_DATASIZE, RILSUPSERVICEDATAPARAMMASK enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_PARAM_SSDI_ALL, RIL_PARAM_SSDI_STATUS, ntddrilapitypes/RIL_PARAM_SSDI_SS_ERROR, netvista.rilsupservicedataparammask, ntddrilapitypes/RIL_PARAM_SSDI_STATUS, RILSUPSERVICEDATAPARAMMASK, RIL_PARAM_SSDI_DATA, ntddrilapitypes/RIL_PARAM_SSDI_DATA, RIL_PARAM_SSDI_ALL, ntddrilapitypes/RILSUPSERVICEDATAPARAMMASK, RIL_PARAM_SSDI_SS_ERROR, RIL_PARAM_SSDI_DATASIZE, RIL_PARAM_SSDI_CC_ERROR, ntddrilapitypes/RIL_PARAM_SSDI_VENDOR_ERROR, ntddrilapitypes/RIL_PARAM_SSDI_CC_ERROR, RIL_PARAM_SSDI_VENDOR_ERROR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILSUPSERVICEDATAPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSUPSERVICEDATAPARAMMASK
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



#### - RIL_PARAM_SSDI_STATUS



#### - RIL_PARAM_SSDI_SS_ERROR



#### - RIL_PARAM_SSDI_CC_ERROR



#### - RIL_PARAM_SSDI_VENDOR_ERROR



#### - RIL_PARAM_SSDI_DATASIZE



#### - RIL_PARAM_SSDI_DATA



#### - RIL_PARAM_SSDI_ALL


