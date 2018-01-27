---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
title: _DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA structure describes stream-state data that specifies the source rectangle of the input stream.
old-location: display\dxvahdddi_stream_state_source_rect_data.htm
old-project: display
ms.assetid: 2ce67fd7-03f6-432c-9229-a99f66f7eb73
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVA2_Structs_82045602-8c6c-4a80-8698-06b34f0ca8d9.xml, d3dumddi/DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA, DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA structure [Display Devices], DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA, display.dxvahdddi_stream_state_source_rect_data, _DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
---

# _DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA structure describes stream-state data that specifies the source rectangle of the input stream. The driver scales the source rectangle within the input surface to the destination rectangle within the output surface. 


## -syntax


````
typedef struct _DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA {
  BOOL Enable;
  RECT SourceRect;
} DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA;
````


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether the driver should use the <b>SourceRect</b> member or the entire input surface as the source. The default value is <b>FALSE</b>, which indicates that the entire input surface is the source. 


### -field SourceRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the source rectangle in the coordinates of the input surface. This member is relevant only when the <b>Enable</b> member is set to <b>TRUE</b>. The default value is (0,0,0,0). 


## -remarks


If the <b>Enable</b> member is set to <b>TRUE</b> and the source rectangle that the <b>SourceRect</b> member specifies is not within the input surface, the intersection of the source rectangle and the input surface is used as the source rectangle. 

The application can use the source rectangle to specify the active rectangle (dirty region) of the source surface.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

