---
UID: NE:rilapitypes.RILGEOSCOPE
title: RILGEOSCOPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgeoscope_2.htm
old-project: netvista
ms.assetid: 821f05f8-cc2c-4567-a1a0-aaa7b535d568
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILGEOSCOPE, RILGEOSCOPE enumeration [Network Drivers Starting with Windows Vista], RIL_GEOSCOPE_CELL, RIL_GEOSCOPE_CELL_IMMEDIATE, RIL_GEOSCOPE_LOCATIONAREA, RIL_GEOSCOPE_MAX, RIL_GEOSCOPE_PLMN, netvista.rilgeoscope_2, rilapitypes/RILGEOSCOPE, rilapitypes/RIL_GEOSCOPE_CELL, rilapitypes/RIL_GEOSCOPE_CELL_IMMEDIATE, rilapitypes/RIL_GEOSCOPE_LOCATIONAREA, rilapitypes/RIL_GEOSCOPE_MAX, rilapitypes/RIL_GEOSCOPE_PLMN
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
-	RILGEOSCOPE
product: Windows
targetos: Windows
req.typenames: RILGEOSCOPE
req.product: Windows 10 or later.
---

# RILGEOSCOPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILGEOSCOPE { 
  RIL_GEOSCOPE_CELL_IMMEDIATE,
  RIL_GEOSCOPE_LOCATIONAREA,
  RIL_GEOSCOPE_PLMN,
  RIL_GEOSCOPE_CELL,
  RIL_GEOSCOPE_MAX
} RILGEOSCOPE;
````


## -enum-fields




### -field RIL_GEOSCOPE_NONE


### -field RIL_GEOSCOPE_CELL_IMMEDIATE


### -field RIL_GEOSCOPE_LOCATIONAREA


### -field RIL_GEOSCOPE_PLMN


### -field RIL_GEOSCOPE_CELL


### -field RIL_GEOSCOPE_MAX

