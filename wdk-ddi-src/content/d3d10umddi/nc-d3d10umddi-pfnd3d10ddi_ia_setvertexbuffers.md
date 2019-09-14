---
UID: NC:d3d10umddi.PFND3D10DDI_IA_SETVERTEXBUFFERS
title: PFND3D10DDI_IA_SETVERTEXBUFFERS (d3d10umddi.h)
description: The IaSetVertexBuffers function sets vertex buffers for an input assembler.
old-location: display\iasetvertexbuffers.htm
ms.assetid: 3d5a7ea1-08c2-4594-93bc-97b985cd16dc
ms.date: 05/10/2018
ms.keywords: IaSetVertexBuffers, IaSetVertexBuffers callback function [Display Devices], PFND3D10DDI_IA_SETVERTEXBUFFERS, PFND3D10DDI_IA_SETVERTEXBUFFERS callback, UserModeDisplayDriverDx10_Functions_12104a04-1497-42c6-a5e1-6573b33a43d3.xml, d3d10umddi/IaSetVertexBuffers, display.iasetvertexbuffers
ms.topic: callback
f1_keywords:
 - "d3d10umddi/IaSetVertexBuffers"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
- d3d10umddi.h
api_name:
- IaSetVertexBuffers
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_IA_SETVERTEXBUFFERS callback function


## -description


The <i>IaSetVertexBuffers</i> function sets vertex buffers for an input assembler.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param StartSlot

The starting vertex buffer to set.

### -param NumBuffers [in]

The total number of buffers to set. 

### -param Arg4

*phBuffers* [in]

An array of handles to the vertex buffers, beginning with the buffer that <i>StartBuffer</i> specifies.
 
### -param Arg5

*pStrides* [in]

An array of values that indicate the sizes, in bytes, from one vertex to the next vertex for each buffer

### -param Arg6

*pOffsets* [in]

An array of values that indicate the offsets, in bytes, into each vertex buffer. 



## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>IaSetVertexBuffers</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

