---
UID: NF:video.VideoPortLogError
title: VideoPortLogError function (video.h)
description: The VideoPortLogError function logs errors to the system event log when a miniport driver detects a hardware error condition during I/O operations.
old-location: display\videoportlogerror.htm
tech.root: display
ms.date: 08/18/2022
keywords: ["VideoPortLogError function"]
ms.keywords: VideoPortLogError, VideoPortLogError function [Display Devices], VideoPort_Functions_18666bd9-b871-4e4c-9f31-bd5cbd505d52.xml, display.videoportlogerror, video/VideoPortLogError
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 2000
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: <= DIRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortLogError
 - video/VideoPortLogError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortLogError
---

# VideoPortLogError function

## -description

The **VideoPortLogError** function logs errors to the system event log when a miniport driver detects a hardware error condition during I/O operations.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's device extension.

### -param Vrp

[optional] Pointer to a [**VIDEO_REQUEST_PACKET**] structure that describes the video request packet (VRP) if one is associated with the error; otherwise NULL.

### -param ErrorCode

Specifies a miniport driver-defined error code that indicates the type of hardware error.

### -param UniqueId

Specifies a unique identifier for the error. This value differentiates the current error from other errors with the same **ErrorCode**. For some miniport drivers, this identifies the line of code where the error was detected; for others, it is a value returned by the hardware.

## -returns

None

## -remarks

Miniport drivers should call **VideoPortLogError** to notify the user if the driver encounters unusual hardware errors during normal operations. Posting such errors to the system event log warns the user that the video adapter might be failing so the user can replace (or reconfigure) the adapter before a total hardware failure occurs.

However, miniport drivers should *not* log errors, such as "failed to detect hardware," that occur frequently during normal operation.

**VideoPortLogError** can be called from a miniport driver's [**HwVidInterrupt**](nc-video-pvideo_hw_interrupt.md) or [**HwVidSynchronizeExecutionCallback**](nc-video-pminiport_synchronize_routine.md) function.

## -see-also

[**VideoDebugPrint**](/previous-versions/ff570170(v=vs.85))
