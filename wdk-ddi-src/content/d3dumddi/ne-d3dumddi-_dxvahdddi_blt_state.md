---
UID: NE:d3dumddi._DXVAHDDDI_BLT_STATE
title: "_DXVAHDDDI_BLT_STATE"
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE enumeration contains values that identify the bit-block transfer (bitblt) state data for a video processor.
old-location: display\dxvahdddi_blt_state.htm
old-project: display
ms.assetid: c17cf4bd-34f0-4bc6-9efc-2f9a649b5438
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA2_Structs_2d8a894a-25be-49c1-bebe-82c7403007db.xml, DXVAHDDDI_BLT_STATE, DXVAHDDDI_BLT_STATE enumeration [Display Devices], DXVAHDDDI_BLT_STATE_ALPHA_FILL, DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR, DXVAHDDDI_BLT_STATE_CONSTRICTION, DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE, DXVAHDDDI_BLT_STATE_PRIVATE, DXVAHDDDI_BLT_STATE_TARGET_RECT, _DXVAHDDDI_BLT_STATE, d3dumddi/DXVAHDDDI_BLT_STATE, d3dumddi/DXVAHDDDI_BLT_STATE_ALPHA_FILL, d3dumddi/DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR, d3dumddi/DXVAHDDDI_BLT_STATE_CONSTRICTION, d3dumddi/DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE, d3dumddi/DXVAHDDDI_BLT_STATE_PRIVATE, d3dumddi/DXVAHDDDI_BLT_STATE_TARGET_RECT, display.dxvahdddi_blt_state
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_BLT_STATE is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
api_name:
-	DXVAHDDDI_BLT_STATE
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_BLT_STATE
---

# _DXVAHDDDI_BLT_STATE enumeration


## -description


The DXVAHDDDI_BLT_STATE enumeration contains values that identify the bit-block transfer (bitblt) state data for a video processor. 


## -enum-fields




### -field DXVAHDDDI_BLT_STATE_TARGET_RECT

The bitblt state data specifies the target rectangle of the output in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563015">DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA</a> structure. 


### -field DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR

The bitblt state data specifies the background color to fill in the target rectangle of the output in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562993">DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA</a> structure. 


### -field DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE

The bitblt state data specifies the color space of the output in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563002">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a> structure. 


### -field DXVAHDDDI_BLT_STATE_ALPHA_FILL

The bitblt state data specifies the alpha-fill mode of the output in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562985">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a> structure. 


### -field DXVAHDDDI_BLT_STATE_CONSTRICTION

The bitblt state data specifies the down sampling of the output in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562997">DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA</a> structure. 


### -field DXVAHDDDI_BLT_STATE_PRIVATE

The bitblt state data specifies the private parameters in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563004">DXVAHDDDI_BLT_STATE_PRIVATE_DATA</a> structure. 


## -remarks



A DXVAHDDDI_BLT_STATE-typed value, which is specified in the <b>State</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543093">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a> structure in a call to the <a href="https://msdn.microsoft.com/6796372c-279d-427c-a2a4-9b7c99494f53">SetVideoProcessBltState</a> function, sets the state of a bitblt for a video processor. Bitblt data that corresponds to the supplied DXVAHDDDI_BLT_STATE-typed value is pointed to by the <b>pData</b> member of D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543093">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562985">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562993">DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562997">DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563002">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563004">DXVAHDDDI_BLT_STATE_PRIVATE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563015">DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA</a>



<a href="https://msdn.microsoft.com/6796372c-279d-427c-a2a4-9b7c99494f53">SetVideoProcessBltState</a>
 

 

