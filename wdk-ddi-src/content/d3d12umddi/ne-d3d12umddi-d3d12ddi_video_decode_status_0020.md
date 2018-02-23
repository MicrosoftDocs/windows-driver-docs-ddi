---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_DECODE_STATUS_0020
title: D3D12DDI_VIDEO_DECODE_STATUS_0020
author: windows-driver-content
description: Contains status values for video decode.
old-location: display\d3d12ddi_video_decode_status.htm
old-project: display
ms.assetid: E7A3944D-142E-450C-B9EE-9190BF264C60
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE, D3D12DDI_VIDEO_DECODE_STATUS_0020_RATE_EXCEEDED, D3D12DDI_VIDEO_DECODE_STATUS_0020_OK, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020_OK, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020_RESTART, D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE_SKIP_DISPLAY, D3D12DDI_VIDEO_DECODE_STATUS_0020 enumeration [Display Devices], D3D12DDI_VIDEO_DECODE_STATUS_0020, display.d3d12ddi_video_decode_status, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE_SKIP_DISPLAY, D3D12DDI_VIDEO_DECODE_STATUS_0020_RESTART, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020_RATE_EXCEEDED, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	D3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_DECODE_STATUS_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_STATUS_0020
---

# D3D12DDI_VIDEO_DECODE_STATUS_0020 enumeration


## -description


Contains status values for video decode.


## -syntax


````
typedef enum D3D12DDI_VIDEO_DECODE_STATUS_0020 { 
  D3D12DDI_VIDEO_DECODE_STATUS_0020_OK                     = 0,
  D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE               = 1,
  D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE_SKIP_DISPLAY  = 2,
  D3D12DDI_VIDEO_DECODE_STATUS_0020_RESTART                = 3,
  D3D12DDI_VIDEO_DECODE_STATUS_0020_RATE_EXCEEDED          = 4
} D3D12DDI_VIDEO_DECODE_STATUS_0020;
````


## -enum-fields




### -field D3D12DDI_VIDEO_DECODE_STATUS_0020_OK

Operation succeeded.


### -field D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE

There was a minor problem in the data format, but the host decoder should continue processing.


### -field D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE_SKIP_DISPLAY

There was a significant problem in the data format. The host decoder should continue processing, but should skip display.


### -field D3D12DDI_VIDEO_DECODE_STATUS_0020_RESTART

There was a severe problem in the data format. The host decoder should restart the entire decoding process, starting at a sequence or random-access entry point.


### -field D3D12DDI_VIDEO_DECODE_STATUS_0020_RATE_EXCEEDED

The bit rate or frame rate supplied to decode stream creation was insufficient for this frame.  When this status is reported, the <b>BitRate</b> member of the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_query_data_video_decode_statistics_0022.md">D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS</a> structure reports a value that can be used to recreate the decode stream at the same frame rate and succeed decoding the failed frames.  Subsequent frames may still fail if those frames exceed the new value.  The reported bit rate is calculated with the frame rate with which the stream was created.


## -see-also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_query_data_video_decode_statistics_0022.md">D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_DECODE_STATUS_0020 enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

