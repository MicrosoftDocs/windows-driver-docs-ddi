---
UID: NE:rilapitypes.RILUICCCARDINFOPARAMMASK
title: RILUICCCARDINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccardinfoparammask_2.htm
old-project: netvista
ms.assetid: f27c7f54-f939-4e9b-a27c-b0137fbb7cec
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILUICCCARDINFOPARAMMASK, RILUICCCARDINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_CARDINFO_ALL, RIL_PARAM_CARDINFO_APPINFO, RIL_PARAM_CARDINFO_ICCID, RIL_PARAM_CARDINFO_NUMAPPS, netvista.riluicccardinfoparammask_2, rilapitypes/RILUICCCARDINFOPARAMMASK, rilapitypes/RIL_PARAM_CARDINFO_ALL, rilapitypes/RIL_PARAM_CARDINFO_APPINFO, rilapitypes/RIL_PARAM_CARDINFO_ICCID, rilapitypes/RIL_PARAM_CARDINFO_NUMAPPS
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILUICCCARDINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCCARDINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILUICCCARDINFOPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILUICCCARDINFOPARAMMASK { 
  RIL_PARAM_CARDINFO_ICCID,
  RIL_PARAM_CARDINFO_NUMAPPS,
  RIL_PARAM_CARDINFO_APPINFO,
  RIL_PARAM_CARDINFO_ALL
} RILUICCCARDINFOPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_CARDINFO_ISVIRTUAL


### -field RIL_PARAM_CARDINFO_ICCID


### -field RIL_PARAM_CARDINFO_NUMAPPS


### -field RIL_PARAM_CARDINFO_APPINFO


### -field RIL_PARAM_CARDINFO_ALL

