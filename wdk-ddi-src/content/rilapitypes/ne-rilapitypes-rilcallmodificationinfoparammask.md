---
UID: NE:rilapitypes.RILCALLMODIFICATIONINFOPARAMMASK
title: RILCALLMODIFICATIONINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationinfoparammask_2.htm
old-project: netvista
ms.assetid: 78726ec3-f777-4165-baec-c2c013e4c86a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLMODIFICATIONINFOPARAMMASK, RILCALLMODIFICATIONINFOPARAMMASK
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
req.alt-api: RILCALLMODIFICATIONINFOPARAMMASK
req.alt-loc: rilapitypes.h
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
req.typenames: RILCALLMODIFICATIONINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILCALLMODIFICATIONINFOPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILCALLMODIFICATIONINFOPARAMMASK { 
  RIL_PARAM_CMI_ID,
  RIL_PARAM_CMI_MODIFICATIONTYPE,
  RIL_PARAM_CMI_OLDCALLTYPE,
  RIL_PARAM_CMI_NEWCALLTYPE,
  RIL_PARAM_CMI_ADDRESS,
  RIL_PARAM_CMI_ALPHAIDENTIFIER,
  RIL_PARAM_CMI_ALL
} RILCALLMODIFICATIONINFOPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_CMI_ID


### -field RIL_PARAM_CMI_MODIFICATIONTYPE


### -field RIL_PARAM_CMI_OLDCALLTYPE


### -field RIL_PARAM_CMI_NEWCALLTYPE


### -field RIL_PARAM_CMI_ADDRESS


### -field RIL_PARAM_CMI_ALPHAIDENTIFIER


### -field RIL_PARAM_CMI_ALL


## -remarks
