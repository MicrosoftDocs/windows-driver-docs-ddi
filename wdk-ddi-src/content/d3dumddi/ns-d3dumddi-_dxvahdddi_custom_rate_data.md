---
UID: NS:d3dumddi._DXVAHDDDI_CUSTOM_RATE_DATA
title: "_DXVAHDDDI_CUSTOM_RATE_DATA"
author: windows-driver-content
description: The DXVAHDDDI_CUSTOM_RATE_DATA structure describes the video content that a decode device processes.
old-location: display\dxvahdddi_custom_rate_data.htm
old-project: display
ms.assetid: 828c4c42-a74f-4737-b850-5c8299e5afd6
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXVA2_Structs_98dcb947-954a-4e8d-adea-3451814e89f9.xml, DXVAHDDDI_CUSTOM_RATE_DATA, DXVAHDDDI_CUSTOM_RATE_DATA structure [Display Devices], _DXVAHDDDI_CUSTOM_RATE_DATA, d3dumddi/DXVAHDDDI_CUSTOM_RATE_DATA, display.dxvahdddi_custom_rate_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_CUSTOM_RATE_DATA is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_CUSTOM_RATE_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_CUSTOM_RATE_DATA
---

# _DXVAHDDDI_CUSTOM_RATE_DATA structure


## -description


The DXVAHDDDI_CUSTOM_RATE_DATA structure describes the video content that a decode device processes. 


## -struct-fields




### -field CustomRate


      [in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563064">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents the input and output frame rate. 
     


### -field OutputFrames

[in] The number of frames that the driver outputs. 


### -field InputInterlaced

[in] A Boolean value that specifies whether the input stream is progressive (frame) or interlaced (field). 


### -field InputFramesOrFields

[in] The number of the input frames or fields. 


## -remarks



The driver can expose custom rates for the frame rate conversion or the inverse telecine. For example, the driver can provide the following information in the members of DXVAHDDDI_CUSTOM_RATE_DATA for the indicated operation:






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563064">DXVAHDDDI_RATIONAL</a>
 

 

