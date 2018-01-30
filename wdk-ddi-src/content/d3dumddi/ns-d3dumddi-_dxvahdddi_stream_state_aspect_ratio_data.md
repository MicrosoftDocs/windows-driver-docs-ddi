---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA
title: "_DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA"
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA structure describes stream-state data that specifies the pixel aspect ratio.
old-location: display\dxvahdddi_stream_state_aspect_ratio_data.htm
old-project: display
ms.assetid: 12d33e2d-63d3-4cc8-9b50-5156132b2e72
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxvahdddi_stream_state_aspect_ratio_data, _DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA, DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA structure [Display Devices], DXVA2_Structs_daab6809-2f81-4892-9f56-c57254047627.xml, d3dumddi/DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA, DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA
---

# _DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA structure describes stream-state data that specifies the pixel aspect ratio. 


## -syntax


````
typedef struct _DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA {
  BOOL               Enable;
  DXVAHDDDI_RATIONAL SourceAspectRatio;
  DXVAHDDDI_RATIONAL DestinationAspectRatio;
} DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA;
````


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether the pixel aspect ratios are available. The default value is <b>FALSE</b>, which indicates that the pixel aspect ratios are not available. 


### -field SourceAspectRatio

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_rational.md">DXVAHDDDI_RATIONAL</a> structure that specifies the pixel aspect ratio of the source. The default is (1, 1). 


### -field DestinationAspectRatio

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_rational.md">DXVAHDDDI_RATIONAL</a> structure that specifies the pixel aspect ratio of the destination. The default is (1, 1). 


## -remarks


The driver might require the source and destination pixel aspect ratios to achieve the best result. 

The <b>DXVAHDDDI_STREAM_STATE_ASPECT_RATIO</b> stream state is best set along with the <b>DXVAHDDDI_STREAM_STATE_FILTER_ANAMORPHIC_SCALING</b> stream state.

Pixel aspect ratios (0, any value) and (any value, 0) are invalid and causes the driver to return an error. 



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_rational.md">DXVAHDDDI_RATIONAL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

