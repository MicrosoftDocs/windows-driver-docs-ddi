---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_FILTER_DATA
title: "_DXVAHDDDI_STREAM_STATE_FILTER_DATA"
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_FILTER_DATA structure describes stream-state data that specifies the filter level.
old-location: display\dxvahdddi_stream_state_filter_data.htm
old-project: display
ms.assetid: 7da30e14-7df4-41e2-b2e3-081c55d68db6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVA2_Structs_e20d3d19-75a9-4539-888f-4c3c73cc02c8.xml, display.dxvahdddi_stream_state_filter_data, DXVAHDDDI_STREAM_STATE_FILTER_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_DATA, DXVAHDDDI_STREAM_STATE_FILTER_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_FILTER_DATA
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	DXVAHDDDI_STREAM_STATE_FILTER_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_FILTER_DATA
---

# _DXVAHDDDI_STREAM_STATE_FILTER_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_FILTER_DATA structure describes stream-state data that specifies the filter level. 


## -syntax


````
typedef struct _DXVAHDDDI_STREAM_STATE_FILTER_DATA {
  BOOL Enable;
  INT  Level;
} DXVAHDDDI_STREAM_STATE_FILTER_DATA;
````


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether the filter is enabled. The default value is <b>FALSE</b>, which indicates that the filter is disabled. 


### -field Level

[in] An INT value that specifies the filter level. The default value is the value from the <b>Default</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_filter_range_data.md">DXVAHDDDI_FILTER_RANGE_DATA</a> structure. 


## -remarks


The level that is specified in the <b>Level</b> member must be within the range that the driver supplies in the members of the <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_filter_range_data.md">DXVAHDDDI_FILTER_RANGE_DATA</a> structure when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPFILTERRANGE value set. 



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_filter_range_data.md">DXVAHDDDI_FILTER_RANGE_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_FILTER_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

