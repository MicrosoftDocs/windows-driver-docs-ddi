---
UID: NS:video._STATUS_BLOCK
title: "_STATUS_BLOCK"
author: windows-driver-content
description: The STATUS_BLOCK structure is a substructure within the VIDEO_REQUEST_PACKET structure. A miniport driver's HwVidStartIO function must set the status block of each VRP that it gets.
old-location: display\status_block.htm
old-project: display
ms.assetid: 8e3126df-d081-4545-a5db-8637ee27f15b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PSTATUS_BLOCK, ,, A, B, C, K, L, O, P, PSTATUS_BLOCK, PSTATUS_BLOCK structure pointer [Display Devices], S, STATUS_BLOCK, STATUS_BLOCK structure [Display Devices], T, U, Video_Structs_90f8dc6a-a666-4976-bc71-edf43b31b6e4.xml, _, _STATUS_BLOCK, display.status_block, video/PSTATUS_BLOCK, video/STATUS_BLOCK"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	video.h
apiname:
-	STATUS_BLOCK
product: Windows
targetos: Windows
req.typenames: STATUS_BLOCK, *PSTATUS_BLOCK
req.product: Windows 10 or later.
---

# _STATUS_BLOCK structure


## -description


The STATUS_BLOCK structure is a substructure within the VIDEO_REQUEST_PACKET structure. A miniport driver's <a href="..\video\nc-video-pvideo_hw_start_io.md">HwVidStartIO</a> function must set the status block of each <a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VRP</a> that it gets.


## -syntax


````
typedef struct _STATUS_BLOCK {
  union {
    VP_STATUS Status;
    PVOID     Pointer;
  };
  ULONG_PTR Information;
} STATUS_BLOCK, *PSTATUS_BLOCK;
````


## -struct-fields




### -field Information

Supplies additional information about the completed operation. The meaning of the value varies according to VRP. Generally, this member is used to return the minimum size required for the input buffer if the VRP passes data in the <b>InputBuffer</b>. Alternatively, it contains the number of bytes of data transferred if the requested operation returns data in the VRP <b>OutputBuffer</b>.


#### - Status

Indicates the result of the requested operation. This member might be one of the following status codes:





#### ERROR_INSUFFICIENT_BUFFER

Either the VRP <b>InputBuffer</b> is too small to provide the data required to process the given request or the <b>OutputBuffer</b> is too small to return the requested data.





#### ERROR_INVALID_FUNCTION

The miniport driver does not handle this request.





#### ERROR_INVALID_PARAMETER

A parameter in the VRP is invalid.





#### ERROR_IO_PENDING

An operation has not yet completed.





#### ERROR_MORE_DATA

The driver has additional data to be returned but has already filled the given VRP <b>OutputBuffer</b>.





#### ERROR_NOT_ENOUGH_MEMORY

There is insufficient memory to process the request.





#### NO_ERROR

The requested operation has been carried out and completed successfully.


#### - Pointer

Should be ignored by the miniport driver. This member of the union exists to guarantee field alignment across 32- and 64-bit systems.


## -see-also

<a href="..\video\nc-video-pvideo_hw_start_io.md">HwVidStartIO</a>



<a href="..\video\ns-video-_video_request_packet.md">VIDEO_REQUEST_PACKET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20STATUS_BLOCK structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

