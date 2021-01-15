---
UID: NC:d3dumddi.PFND3DDDI_DECODEBEGINFRAME
title: PFND3DDDI_DECODEBEGINFRAME (d3dumddi.h)
description: The DecodeBeginFrame function notifies the user-mode display driver that decoding can begin on the specified Microsoft DirectX Video Accelerator (VA) decode device.
old-location: display\decodebeginframe.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DECODEBEGINFRAME callback function"]
ms.keywords: DecodeBeginFrame, DecodeBeginFrame callback function [Display Devices], PFND3DDDI_DECODEBEGINFRAME, PFND3DDDI_DECODEBEGINFRAME callback, UserModeDisplayDriver_Functions_3fab4933-b0fb-4a3f-8316-2c698775dda5.xml, d3dumddi/DecodeBeginFrame, display.decodebeginframe
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_DECODEBEGINFRAME
 - d3dumddi/PFND3DDDI_DECODEBEGINFRAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_DECODEBEGINFRAME
product:
 - Windows
---

# PFND3DDDI_DECODEBEGINFRAME callback function


## -description

The <b>DecodeBeginFrame</b> function notifies the user-mode display driver that decoding can begin on the specified Microsoft DirectX Video Accelerator (VA) decode device.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decodebeginframe">D3DDDIARG_DECODEBEGINFRAME</a> structure that describes information for the DirectX VA decoder to start decoding a frame.

## -returns

<b>DecodeBeginFrame</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | Decoding successfully began. | 
| **E_OUTOFMEMORY** | [DecodeBeginFrame]()  could not allocate the required memory for it to complete. |

## -remarks

The <b>DecodeBeginFrame</b> function notifies the user-mode display driver that its <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decodeexecute">DecodeExecute</a> function can be called on the specified decode device.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decodebeginframe">D3DDDIARG_DECODEBEGINFRAME</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decodeexecute">DecodeExecute</a>

