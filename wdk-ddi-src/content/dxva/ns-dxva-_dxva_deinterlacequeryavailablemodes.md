---
UID: NS:dxva._DXVA_DeinterlaceQueryAvailableModes
title: _DXVA_DeinterlaceQueryAvailableModes (dxva.h)
description: The DXVA_DeinterlaceQueryAvailableModes structure describes the available deinterlacing or frame-rate conversion modes for a particular input video format.
old-location: display\dxva_deinterlacequeryavailablemodes.htm
tech.root: display
ms.assetid: c754f540-19ff-491f-89ec-63d3306c4068
ms.date: 05/10/2018
keywords: ["_DXVA_DeinterlaceQueryAvailableModes structure"]
ms.keywords: DXVA_DeinterlaceQueryAvailableModes, DXVA_DeinterlaceQueryAvailableModes structure [Display Devices], _DXVA_DeinterlaceQueryAvailableModes, display.dxva_deinterlacequeryavailablemodes, dxva/DXVA_DeinterlaceQueryAvailableModes, dxvaref_9c2ffe96-e286-4f0f-bb6b-57bc6ee64b2c.xml
f1_keywords:
 - "dxva/DXVA_DeinterlaceQueryAvailableModes"
req.header: dxva.h
req.include-header: Dxva.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_DeinterlaceQueryAvailableModes
product:
- Windows
targetos: Windows
req.typenames: DXVA_DeinterlaceQueryAvailableModes
---

# _DXVA_DeinterlaceQueryAvailableModes structure


## -description


The DXVA_DeinterlaceQueryAvailableModes structure describes the available deinterlacing or frame-rate conversion modes for a particular input video format.


## -struct-fields




### -field Size

Indicates the size of this structure.


### -field NumGuids

Indicates the number of GUIDs that are returned in the <b>Guids</b> member for the available modes.


### -field Guids

An array of GUIDs that are returned for the available deinterlace modes.


## -remarks



The driver receives the DXVA_DeinterlaceQueryAvailableModes structure with the <b>Size</b> member assigned, assigns values to the remaining members, and returns DXVA_DeinterlaceQueryAvailableModes to the renderer.

There is a GUID for each deinterlace and frame conversion mode returned by the driver. The GUIDs should be returned in order of descending quality (that is, the highest quality mode should occupy the first element of the GUID array returned). 



