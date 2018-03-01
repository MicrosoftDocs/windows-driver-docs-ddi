---
UID: NE:ntddrilapitypes.RILCALLMODIFICATIONINFOPARAMMASK
title: RILCALLMODIFICATIONINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationinfoparammask.htm
old-project: netvista
ms.assetid: 1282f158-9e41-4789-abe9-181f367ea235
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLMODIFICATIONINFOPARAMMASK, RILCALLMODIFICATIONINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_CMI_ADDRESS, RIL_PARAM_CMI_ALL, RIL_PARAM_CMI_ALPHAIDENTIFIER, RIL_PARAM_CMI_ID, RIL_PARAM_CMI_MODIFICATIONTYPE, RIL_PARAM_CMI_NEWCALLTYPE, RIL_PARAM_CMI_OLDCALLTYPE, netvista.rilcallmodificationinfoparammask, ntddrilapitypes/RILCALLMODIFICATIONINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_CMI_ADDRESS, ntddrilapitypes/RIL_PARAM_CMI_ALL, ntddrilapitypes/RIL_PARAM_CMI_ALPHAIDENTIFIER, ntddrilapitypes/RIL_PARAM_CMI_ID, ntddrilapitypes/RIL_PARAM_CMI_MODIFICATIONTYPE, ntddrilapitypes/RIL_PARAM_CMI_NEWCALLTYPE, ntddrilapitypes/RIL_PARAM_CMI_OLDCALLTYPE
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILCALLMODIFICATIONINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILCALLMODIFICATIONINFOPARAMMASK
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




### -field RIL_PARAM_CMI_EXECUTOR


### -field RIL_PARAM_CMI_ID


### -field RIL_PARAM_CMI_MODIFICATIONTYPE


### -field RIL_PARAM_CMI_OLDCALLTYPE


### -field RIL_PARAM_CMI_NEWCALLTYPE


### -field RIL_PARAM_CMI_ADDRESS


### -field RIL_PARAM_CMI_ALPHAIDENTIFIER


### -field RIL_PARAM_CMI_ALL

