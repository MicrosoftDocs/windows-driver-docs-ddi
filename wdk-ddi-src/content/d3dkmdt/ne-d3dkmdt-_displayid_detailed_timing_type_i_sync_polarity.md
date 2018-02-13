---
UID: NE:d3dkmdt._DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY
title: "_DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY"
author: windows-driver-content
description: The DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration indicates the display device's sync polarity (whether the sync signal is positive or negative).
old-location: display\displayid_detailed_timing_type_i_sync_polarity.htm
old-project: display
ms.assetid: 6563d4f7-3750-49c1-80f5-14a839e70cb7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DIDDT1_Sync_Negative, d3dkmdt/_DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY, display.displayid_detailed_timing_type_i_sync_polarity, d3dkmdt/DIDDT1_Sync_Negative, d3dkmdt/DIDDT1_Sync_Positive, DmEnums_7a2bc957-2ae3-4a38-bbe7-8e3e52994e5d.xml, _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration [Display Devices], _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY, DIDDT1_Sync_Positive
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	_DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY
product: Windows
targetos: Windows
req.typenames: 
---

# _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration


## -description


The DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration indicates the display device's sync polarity (whether the sync signal is positive or negative).


## -syntax


````
enum _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY {
  DIDDT1_Sync_Positive  = 0, 
  DIDDT1_Sync_Negative  = 1 

};
````


## -enum-fields




### -field DIDDT1_Sync_Positive

Indicates that the sync polarity is positive.


### -field DIDDT1_Sync_Negative

Indicates that the sync polarity is negative.

