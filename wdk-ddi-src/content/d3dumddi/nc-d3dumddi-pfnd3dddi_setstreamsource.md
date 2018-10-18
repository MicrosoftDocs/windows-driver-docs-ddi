---
UID: NC:d3dumddi.PFND3DDDI_SETSTREAMSOURCE
title: PFND3DDDI_SETSTREAMSOURCE
author: windows-driver-content
description: The SetStreamSource function binds a portion of a vertex stream source to a vertex buffer.
old-location: display\setstreamsource.htm
tech.root: display
ms.assetid: 669dbabc-91fb-40f9-a034-11c3c2e70436
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_SETSTREAMSOURCE, PFND3DDDI_SETSTREAMSOURCE callback, SetStreamSource, SetStreamSource callback function [Display Devices], UserModeDisplayDriver_Functions_c84f438f-92b5-4d01-8d27-275deedc29e4.xml, d3dumddi/SetStreamSource, display.setstreamsource
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	SetStreamSource
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETSTREAMSOURCE callback function


## -description


The <i>SetStreamSource</i> function binds a portion of a vertex stream source to a vertex buffer. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543352">D3DDDIARG_SETSTREAMSOURCE</a> structure that specifies the portion of the vertex stream source to bind.


## -returns



<i>SetStreamSource</i> returns S_OK or an appropriate error result if the portion of the vertex stream source is not successfully bound.




## -remarks



The Microsoft Direct3D runtime calls the user-mode display driver's <i>SetStreamSource</i> function to store vertex data of multiple vertex formats in a single vertex data stream. The runtime notifies the driver of where vertex data of a particular format is located in the vertex data stream by supplying the stream offset, in bytes, to the beginning of that vertex data. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543352">D3DDDIARG_SETSTREAMSOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

