---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_FILTER_DATA
title: "_DXVAHDDDI_STREAM_STATE_FILTER_DATA"
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_FILTER_DATA structure describes stream-state data that specifies the filter level.
old-location: display\dxvahdddi_stream_state_filter_data.htm
old-project: display
ms.assetid: 7da30e14-7df4-41e2-b2e3-081c55d68db6
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXVA2_Structs_e20d3d19-75a9-4539-888f-4c3c73cc02c8.xml, DXVAHDDDI_STREAM_STATE_FILTER_DATA, DXVAHDDDI_STREAM_STATE_FILTER_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_FILTER_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_DATA, display.dxvahdddi_stream_state_filter_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_FILTER_DATA is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_STREAM_STATE_FILTER_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_FILTER_DATA
---

# _DXVAHDDDI_STREAM_STATE_FILTER_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_FILTER_DATA structure describes stream-state data that specifies the filter level. 


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether the filter is enabled. The default value is <b>FALSE</b>, which indicates that the filter is disabled. 


### -field Level

[in] An INT value that specifies the filter level. The default value is the value from the <b>Default</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563055">DXVAHDDDI_FILTER_RANGE_DATA</a> structure. 


## -remarks



The level that is specified in the <b>Level</b> member must be within the range that the driver supplies in the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563055">DXVAHDDDI_FILTER_RANGE_DATA</a> structure when the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPFILTERRANGE value set. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563055">DXVAHDDDI_FILTER_RANGE_DATA</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

