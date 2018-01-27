---
UID: NE:ntddrilapitypes.RILGEOSCOPE
title: RILGEOSCOPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgeoscope.htm
old-project: netvista
ms.assetid: 5dc49d01-54d2-48d3-8649-96262b890fc5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_GEOSCOPE_PLMN, ntddrilapitypes/RIL_GEOSCOPE_LOCATIONAREA, netvista.rilgeoscope, RIL_GEOSCOPE_CELL, ntddrilapitypes/RIL_GEOSCOPE_MAX, RILGEOSCOPE, ntddrilapitypes/RILGEOSCOPE, ntddrilapitypes/RIL_GEOSCOPE_CELL_IMMEDIATE, RIL_GEOSCOPE_LOCATIONAREA, RIL_GEOSCOPE_PLMN, RIL_GEOSCOPE_MAX, ntddrilapitypes/RIL_GEOSCOPE_CELL, RIL_GEOSCOPE_CELL_IMMEDIATE, RILGEOSCOPE enumeration [Network Drivers Starting with Windows Vista]
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
-	RILGEOSCOPE
product: Windows
targetos: Windows
req.typenames: RILGEOSCOPE
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


