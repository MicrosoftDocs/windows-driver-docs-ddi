---
UID: NE:rilapitypes.RILSIGNALQUALITYPARAMMASK
title: RILSIGNALQUALITYPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsignalqualityparammask_2.htm
old-project: netvista
ms.assetid: be6c46bb-9c14-4daf-b76a-679d71269965
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_SQ_SIGNALSTRENGTH, rilapitypes/RIL_PARAM_SQ_NUMSIGNALBARS, RIL_PARAM_SQ_NUMSIGNALBARS, rilapitypes/RIL_PARAM_SQ_SIGNALSTRENGTH, RIL_PARAM_SQ_ALL, rilapitypes/RIL_PARAM_SQ_ALL, RIL_PARAM_SQ_SYSTEMTYPE, netvista.rilsignalqualityparammask_2, RILSIGNALQUALITYPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RILSIGNALQUALITYPARAMMASK, RILSIGNALQUALITYPARAMMASK, RIL_PARAM_SQ_SNR, rilapitypes/RIL_PARAM_SQ_SNR, rilapitypes/RIL_PARAM_SQ_SYSTEMTYPE
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
-	RILSIGNALQUALITYPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSIGNALQUALITYPARAMMASK
req.product: Windows 10 or later.
---

# RILSIGNALQUALITYPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILSIGNALQUALITYPARAMMASK { 
  RIL_PARAM_SQ_SYSTEMTYPE,
  RIL_PARAM_SQ_NUMSIGNALBARS,
  RIL_PARAM_SQ_SIGNALSTRENGTH,
  RIL_PARAM_SQ_SNR,
  RIL_PARAM_SQ_ALL
} RILSIGNALQUALITYPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_SQ_EXECUTOR



### -field RIL_PARAM_SQ_SYSTEMTYPE



### -field RIL_PARAM_SQ_NUMSIGNALBARS



### -field RIL_PARAM_SQ_SIGNALSTRENGTH



### -field RIL_PARAM_SQ_SNR



### -field RIL_PARAM_SQ_ALL


