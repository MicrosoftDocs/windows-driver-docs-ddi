---
UID: NC:d3dumddi.PFND3DDDI_VALIDATEDEVICE
title: PFND3DDDI_VALIDATEDEVICE (d3dumddi.h)
description: The ValidateDevice function returns the number of passes in which the hardware can perform the blending operations that are specified in the current state.
old-location: display\validatedevice.htm
tech.root: display
ms.assetid: 058696e0-be4a-45f3-b3e8-55abccdce3ce
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_VALIDATEDEVICE, PFND3DDDI_VALIDATEDEVICE callback, UserModeDisplayDriver_Functions_37e253ca-1d0f-4896-aaad-4c36053877c5.xml, ValidateDevice, ValidateDevice callback function [Display Devices], d3dumddi/ValidateDevice, display.validatedevice
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
- ValidateDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_VALIDATEDEVICE callback function


## -description


The <i>ValidateDevice</i> function returns the number of passes in which the hardware can perform the blending operations that are specified in the current state.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_validatetexturestagestate">D3DDDIARG_VALIDATETEXTURESTAGESTATE</a> structure that receives the number of passes in which the hardware can perform the blending operations.


## -returns



<i>ValidateDevice</i> returns S_OK or an appropriate error result if the number of necessary hardware passes is not successfully received.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_validatetexturestagestate">D3DDDIARG_VALIDATETEXTURESTAGESTATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
 

 

