---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA
title: "_DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA"
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA structure describes stream-state data that specifies the destination rectangle. The driver scales the source rectangle within the input surface to the destination rectangle within the output surface.
old-location: display\dxvahdddi_stream_state_destination_rect_data.htm
old-project: display
ms.assetid: 82f0cb12-fc0e-4627-af50-df4697f6764f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, A, C, D, DXVA2_Structs_3b88b3f0-9b31-46c6-8725-514f227b12a1.xml, DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA, DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA structure [Display Devices], E, H, I, M, N, O, R, S, T, V, X, _, _DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA, display.dxvahdddi_stream_state_destination_rect_data"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA
---

# _DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA structure describes stream-state data that specifies the destination rectangle. The driver scales the source rectangle within the input surface to the destination rectangle within the output surface. 


## -syntax


````
typedef struct _DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA {
  BOOL Enable;
  RECT DestinationRect;
} DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA;
````


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether the driver should use the <b>DestinationRect</b> member or the entire target rectangle as the destination. The default value is <b>FALSE</b>, which indicates that the entire target rectangle is the destination. 


### -field DestinationRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the coordinates of the destination rectangle relevant to the target rectangle. This member is relevant only when the <b>Enable</b> member is set to <b>TRUE</b>. The default value is empty (0,0,0,0). 


## -remarks



If the <b>Enable</b> member is set to <b>TRUE</b> and the destination rectangle that the <b>DestinationRect</b> member specifies is not within the target rectangle, the intersection of the destination rectangle and the target rectangle is used as the destination rectangle. 

The application can use the destination rectangle to specify the active rectangle (dirty region) of the destination surface.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

