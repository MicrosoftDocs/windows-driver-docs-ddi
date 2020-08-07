---
UID: NS:dxva._DXVA_ProcAmpControlQueryRange
title: _DXVA_ProcAmpControlQueryRange (dxva.h)
description: The DXVA_ProcAmpControlQueryRange structure contains the minimum, maximum, step size, and default value for each ProcAmp property.
old-location: display\dxva_procampcontrolqueryrange.htm
tech.root: display
ms.assetid: 934b69cd-f54d-4706-bcb6-8d9e25ea3367
ms.date: 05/10/2018
keywords: ["DXVA_ProcAmpControlQueryRange structure"]
ms.keywords: "*LPDXVA_ProcAmpControlQueryRange, DXVA_ProcAmpControlQueryRange, DXVA_ProcAmpControlQueryRange structure [Display Devices], LPDXVA_ProcAmpControlQueryRange, LPDXVA_ProcAmpControlQueryRange structure pointer [Display Devices], _DXVA_ProcAmpControlQueryRange, display.dxva_procampcontrolqueryrange, dxva/DXVA_ProcAmpControlQueryRange, dxva/LPDXVA_ProcAmpControlQueryRange, dxvaref_5122c77d-0d7a-42a4-be26-f03993fb52db.xml"
f1_keywords:
 - "dxva/DXVA_ProcAmpControlQueryRange"
 - "DXVA_ProcAmpControlQueryRange"
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: DirectX 9.0 and later versions only.
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
- DXVA_ProcAmpControlQueryRange
targetos: Windows
req.typenames: DXVA_ProcAmpControlQueryRange, *LPDXVA_ProcAmpControlQueryRange
---

# _DXVA_ProcAmpControlQueryRange structure


## -description


The DXVA_ProcAmpControlQueryRange structure contains the minimum, maximum, step size, and default value for each ProcAmp property.


## -struct-fields




### -field Size

Specifies the size of this structure in bytes.


### -field ProcAmpControlProp

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_procampcontrolprop">DXVA_ProcAmpControlProp</a> structure that indicates the supported ProcAmp control properties.


### -field VideoDesc

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_videodesc">DXVA_VideoDesc</a> structure that provides the driver with a description of the video that the ProcAmp adjustment is going to be applied to. Drivers may adjust their ProcAmp feature support for particular video streams.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_procampcontrolprop">DXVA_ProcAmpControlProp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_videodesc">DXVA_VideoDesc</a>
 

 

