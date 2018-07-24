---
UID: NS:dxva._DXVA_DeinterlaceQueryModeCaps
title: "_DXVA_DeinterlaceQueryModeCaps"
author: windows-driver-content
description: The DXVA_DeinterlaceQueryModeCaps structure describes a deinterlacing mode.
old-location: display\dxva_deinterlacequerymodecaps.htm
tech.root: display
ms.assetid: 4978e4f6-23e3-4381-be4e-550292101013
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXVA_DeinterlaceQueryModeCaps, DXVA_DeinterlaceQueryModeCaps structure [Display Devices], _DXVA_DeinterlaceQueryModeCaps, display.dxva_deinterlacequerymodecaps, dxva/DXVA_DeinterlaceQueryModeCaps, dxvaref_a9b0a8a8-0a11-417c-a356-6b39cb1f7ddb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxva.h
api_name:
-	DXVA_DeinterlaceQueryModeCaps
product:
- Windows
targetos: Windows
req.typenames: DXVA_DeinterlaceQueryModeCaps
---

# _DXVA_DeinterlaceQueryModeCaps structure


## -description


The DXVA_DeinterlaceQueryModeCaps structure describes a deinterlacing mode. 


## -struct-fields




### -field Size

Indicates the size of this structure.


### -field Guid

Specifies for which mode of deinterlacing the driver should return capabilities.


### -field VideoDesc

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564070">DXVA_VideoDesc</a> structure that describes the type of video that is to be deinterlaced.


## -remarks



The driver receives the DXVA_DeinterlaceQueryModeCaps structure with all members assigned in a query for capabilities about a particular deinterlacing mode. The driver returns capabilities in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563939">DXVA_DeinterlaceCaps</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563939">DXVA_DeinterlaceCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563951">DXVA_DeinterlaceQueryAvailableModes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564070">DXVA_VideoDesc</a>
 

 

