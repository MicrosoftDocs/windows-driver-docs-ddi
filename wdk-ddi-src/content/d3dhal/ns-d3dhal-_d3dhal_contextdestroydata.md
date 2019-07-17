---
UID: NS:d3dhal._D3DHAL_CONTEXTDESTROYDATA
title: _D3DHAL_CONTEXTDESTROYDATA (d3dhal.h)
description: The D3DHAL_CONTEXTDESTROYDATA structure contains the information that the D3dContextDestroy function requires to delete a context.
old-location: display\d3dhal_contextdestroydata.htm
tech.root: display
ms.assetid: 1224f634-b349-4098-a6ad-cbf18742ffb7
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_CONTEXTDESTROYDATA, D3DHAL_CONTEXTDESTROYDATA, D3DHAL_CONTEXTDESTROYDATA structure [Display Devices], LPD3DHAL_CONTEXTDESTROYDATA, LPD3DHAL_CONTEXTDESTROYDATA structure pointer [Display Devices], _D3DHAL_CONTEXTDESTROYDATA, d3dhal/D3DHAL_CONTEXTDESTROYDATA, d3dhal/LPD3DHAL_CONTEXTDESTROYDATA, d3dstrct_7ae0080d-0578-43e2-9ddc-0dd7df1a4fcd.xml, display.d3dhal_contextdestroydata"
ms.topic: struct
f1_keywords:
 - "d3dhal/D3DHAL_CONTEXTDESTROYDATA"
req.header: d3dhal.h
req.include-header: D3dhal.h
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
- d3dhal.h
api_name:
- D3DHAL_CONTEXTDESTROYDATA
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_CONTEXTDESTROYDATA
---

# _D3DHAL_CONTEXTDESTROYDATA structure


## -description


The D3DHAL_CONTEXTDESTROYDATA structure contains the information that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_contextdestroycb">D3dContextDestroy</a> function requires to delete a context.


## -struct-fields




### -field dwhContext

Specifies the handle to the context to be destroyed.


### -field ddrval

Specifies the location where the driver writes the return code for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_contextdestroycb">D3dContextDestroy</a>. D3D_OK indicates success. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/return-codes-for-direct3d-driver-callbacks">Return Codes for Direct3D Driver Callbacks</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_contextdestroycb">D3dContextDestroy</a>
 

 

