---
UID: NC:d3dumddi.PFND3DDDI_OPENRESOURCE
title: PFND3DDDI_OPENRESOURCE (d3dumddi.h)
description: The OpenResource function informs the driver that a shared resource is opened.
old-location: display\openresource.htm
tech.root: display
ms.assetid: e3f5cec2-391b-40f9-8a4b-afe6b8de2954
ms.date: 05/10/2018
ms.keywords: OpenResource, OpenResource callback function [Display Devices], PFND3DDDI_OPENRESOURCE, PFND3DDDI_OPENRESOURCE callback, UserModeDisplayDriver_Functions_57f3d196-70e6-475e-86ca-bb6d20aca568.xml, d3dumddi/OpenResource, display.openresource
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- UserDefined
api_location:
- d3dumddi.h
api_name:
- OpenResource
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_OPENRESOURCE callback function


## -description


The <i>OpenResource</i> function informs the driver that a shared resource is opened.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context) that is used to open the resource.


### -param *

*pResource* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543232">D3DDDIARG_OPENRESOURCE</a> structure that describes the resource that is opened.


## -returns



<i>OpenResource</i> returns S_OK or an appropriate error result if the resource is not successfully opened.




## -remarks



The Microsoft Direct3D runtime calls the user-mode display driver's <i>OpenResource</i> function to inform the user-mode display driver that a shared resource is opened. The driver should store any information that is required to describe the resource and return a unique handle in the <b>hResource</b> member of the D3DDDIARG_OPENRESOURCE structure (pointed to by the <i>pResource</i> parameter) that identifies the new resource in subsequent calls that the Direct3D runtime makes to the driver. The private driver data that is passed to <i>OpenResource</i> is the same private driver data that was passed to the display miniport driver's <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function when the resource was created.

For more information about creating and destroying resources, see <a href="https://msdn.microsoft.com/d443bdc3-1c5a-4372-9e6a-b8a4d21499b9">Handling Resource Creation and Destruction</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543232">D3DDDIARG_OPENRESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544599">D3DDDI_OPENALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>
 

 

