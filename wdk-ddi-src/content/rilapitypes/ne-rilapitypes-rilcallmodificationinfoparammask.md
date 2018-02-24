---
UID: NE:rilapitypes.RILCALLMODIFICATIONINFOPARAMMASK
title: RILCALLMODIFICATIONINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationinfoparammask_2.htm
old-project: netvista
ms.assetid: 78726ec3-f777-4165-baec-c2c013e4c86a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_PARAM_CMI_NEWCALLTYPE, rilapitypes/RILCALLMODIFICATIONINFOPARAMMASK, rilapitypes/RIL_PARAM_CMI_ALPHAIDENTIFIER, RILCALLMODIFICATIONINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_CMI_ID, RIL_PARAM_CMI_MODIFICATIONTYPE, rilapitypes/RIL_PARAM_CMI_ADDRESS, rilapitypes/RIL_PARAM_CMI_NEWCALLTYPE, RIL_PARAM_CMI_ALL, RIL_PARAM_CMI_ID, RIL_PARAM_CMI_ADDRESS, RILCALLMODIFICATIONINFOPARAMMASK, RIL_PARAM_CMI_ALPHAIDENTIFIER, netvista.rilcallmodificationinfoparammask_2, RIL_PARAM_CMI_OLDCALLTYPE, rilapitypes/RIL_PARAM_CMI_OLDCALLTYPE, rilapitypes/RIL_PARAM_CMI_ALL, rilapitypes/RIL_PARAM_CMI_MODIFICATIONTYPE
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
-	RILCALLMODIFICATIONINFOPARAMMASK
product: Windows
targetos: Windows
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




### -field RIL_PARAM_CMI_EXECUTOR


### -field RIL_PARAM_CMI_ID


### -field RIL_PARAM_CMI_MODIFICATIONTYPE


### -field RIL_PARAM_CMI_OLDCALLTYPE


### -field RIL_PARAM_CMI_NEWCALLTYPE


### -field RIL_PARAM_CMI_ADDRESS


### -field RIL_PARAM_CMI_ALPHAIDENTIFIER


### -field RIL_PARAM_CMI_ALL

