---
UID: NS:iddcx.IDDCX_FRAME_STATISTICS
title: IDDCX_FRAME_STATISTICS
author: windows-driver-content
description: Gives information about the current frame being processed.
old-location: display\iddcx_frame_statistics.htm
tech.root: display
ms.assetid: 5099ff37-eed9-44fd-8254-3828b8c5d8bd
ms.date: 5/10/2018
ms.keywords: IDDCX_FRAME_STATISTICS, IDDCX_FRAME_STATISTICS structure [Display Devices], display.iddcx_frame_statistics, iddcx/IDDCX_FRAME_STATISTICS
ms.topic: struct
req.header: iddcx.h
req.include-header: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IDDCX_FRAME_STATISTICS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDDCX_FRAME_STATISTICS structure


## -description


Gives information about the current frame being processed.
             


## -struct-fields




### -field Size


                     Total size of the structure
                 


### -field PresentationFrameNumber


                     The frame number provided in the ReleaseAndAcquireBuffer call


### -field FrameStatus


                     Indicates the overall status of processing this frame
                 


### -field ReEncodeNumber

Zero based number to indicate the number of times the same frame has been encoded and sent. Re-encodes can be the result of the OS providing the same frame and frame number to the driver to encode or the driver having to re-encode outside of the normal OS presentation to satisfy the protocol.


### -field FrameSliceTotal


                     Indicates the number of slices the driver processes the frame in. If slices are not used, then this should be set to the value one
                 


### -field CurrentSlice


                     Indicates the zero based slice number being reported. If slicing is not supported, then the driver should always set this to the value zero
                 


### -field FrameAcquireQpcTime


                     System Qpc time the driver acquired the buffer from the OS
                 


### -field FrameProcessingStepsCount


                     The size of the frame step array pointed to by pFrameParts
                 


### -field pFrameProcessingStep


                     Array of frame processing steps the driver performed
                 


### -field SendStartQpcTime


                     Marks the time when the driver started transmission for this slice to the device

<div class="alert"><b>Note</b>  NOTE : This marks the time the driver started calling the transmit API's, not when the data actually starts being transmitted</div>
<div> </div>

### -field SendStopQpcTime


                     Marks the time when the driver started transmission for this slice to the device

<div class="alert"><b>Note</b>  This marks the time the driver started calling the transmit API's, not when the data actually starts being transmitted</div>
<div> </div>

### -field SendCompleteQpcTime


                     Marks the time when the send was reported as complete by the OS. This is an optional time stamp that can be used if the driver uses asynchronous transmit API and a completion routine. In the event the driver does not have an asynchronous completion routine, this value should be set to zero
                 


### -field Flags


                     Frame statistic flags
                 


### -field ProcessedPixelCount


                     
                 The total number of pixels processed in this frame


### -field FrameSizeInBytes


                     Total size of the data send to device for this frame, this includes all the slices
                 

