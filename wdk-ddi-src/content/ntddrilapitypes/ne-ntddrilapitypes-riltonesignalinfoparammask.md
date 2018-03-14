---
UID: NE:ntddrilapitypes.RILTONESIGNALINFOPARAMMASK
title: RILTONESIGNALINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltonesignalinfoparammask.htm
old-project: netvista
ms.assetid: 5ebacb12-4ccd-4e92-ba73-b79c1969eb4f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILTONESIGNALINFOPARAMMASK, RILTONESIGNALINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_TONESIGNAL_All, RIL_PARAM_TONESIGNAL_EXECUTOR, RIL_PARAM_TONESIGNAL_GPP2ISDNALERTING, RIL_PARAM_TONESIGNAL_GPP2TONE, netvista.riltonesignalinfoparammask, ntddrilapitypes/RILTONESIGNALINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_TONESIGNAL_All, ntddrilapitypes/RIL_PARAM_TONESIGNAL_EXECUTOR, ntddrilapitypes/RIL_PARAM_TONESIGNAL_GPP2ISDNALERTING, ntddrilapitypes/RIL_PARAM_TONESIGNAL_GPP2TONE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	RILTONESIGNALINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILTONESIGNALINFOPARAMMASK
---

# RILTONESIGNALINFOPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILTONESIGNALINFOPARAMMASK { 
  RIL_PARAM_TONESIGNAL_GPP2TONE,
  RIL_PARAM_TONESIGNAL_GPP2ISDNALERTING,
  RIL_PARAM_TONESIGNAL_EXECUTOR,
  RIL_PARAM_TONESIGNAL_All
} RILTONESIGNALINFOPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_TONESIGNAL_GPPTONE


### -field RIL_PARAM_TONESIGNAL_GPP2TONE


### -field RIL_PARAM_TONESIGNAL_GPP2ISDNALERTING


### -field RIL_PARAM_TONESIGNAL_EXECUTOR


### -field RIL_PARAM_TONESIGNAL_All

