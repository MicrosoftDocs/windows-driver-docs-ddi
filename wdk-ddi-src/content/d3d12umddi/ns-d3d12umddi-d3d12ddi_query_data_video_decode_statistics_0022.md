---
UID: NS:d3d12umddi.D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022
title: D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022
author: windows-driver-content
description: Video decode statistics for a query.
old-location: display\d3d12ddi_query_data_video_decode_statistics.htm
old-project: display
ms.assetid: F58AB9E1-4061-46B8-8137-319DF30D9CA7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 0, 1, 2, 3, A, C, D, D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022, D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022 structure [Display Devices], E, I, O, Q, R, S, T, U, V, Y, _, d3d12umddi/D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022, display.d3d12ddi_query_data_video_decode_statistics"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022
---

# D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022 structure


## -description


Video decode statistics for a query.


## -syntax


````
typedef struct D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022 {
  UINT64        Status;
  UINT64        NumMacroblocksAffected;
  DXGI_RATIONAL FrameRate;
  UINT          BitRate;
} D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022;
````


## -struct-fields




### -field Status

Specifies the status of an operation as a <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_status_0020.md">D3D12DDI_VIDEO_DECODE_STATUS</a> value.


### -field NumMacroblocksAffected

The number of blocks affected. If the <b>Status</b> value  is not 0, this member contains an estimate from the accelerator of the number of super-blocks in the decoded frame that were adversely affected by the reported problem. If the accelerator does not provide an estimate, the value is 0xFFFFFFFFFFFFFFFF. 


### -field FrameRate


### -field BitRate

When the <b>Status</b> value returned is <b>D3D12DDI_VIDEO_DECODE_STATUS_RATE_EXCEEDED</b>, this member reports the required bit rate.  This value may be used to recreate the decode stream and try again.  The updated value is relative to the frame rate with which the stream was created.  A value of zero (0) is valid to indicate that the worst case bit rate should be assumed.  
For all other <b>Status</b> values, <b>BitRate</b> is not used and is set to zero.



## -see-also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_status_0020.md">D3D12DDI_VIDEO_DECODE_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

