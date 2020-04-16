---
UID: NS:usbioctl._USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION
title: _USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION (usbioctl.h)
description: Stores the frame and microframe numbers and the calculated system QPC values. This structure is used in the IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC request.
old-location: buses\usb_frame_number_and_qpc_for_time_sync_information.htm
tech.root: usbref
ms.assetid: F602B738-4D04-4A75-BE69-CFEC4F76904C
ms.date: 05/07/2018
keywords: ["_USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION structure"]
ms.keywords: "*PUSB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION, PUSB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION, PUSB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION structure pointer [Buses], USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION, USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION structure [Buses], _USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION, buses.usb_frame_number_and_qpc_for_time_sync_information, usbioctl/PUSB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION, usbioctl/USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION"
f1_keywords:
 - "usbioctl/USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION"
req.header: usbioctl.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION, *PUSB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION
---

# _USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION structure


## -description


Stores the frame and microframe numbers and the calculated system QPC values. This structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_frame_number_and_qpc_for_time_sync">IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC</a> request.


## -struct-fields




### -field TimeTrackingHandle

The time racking handle received in the previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_stop_tracking_for_time_sync">IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC</a> request.


### -field InputFrameNumber

A 32-bit USB bus frame number. 


### -field InputMicroFrameNumber

A 3-bit value received from the hardware. 


### -field QueryPerformanceCounterAtInputFrameOrMicroFrame

A value predicted by the USB driver stack that represents the system QPC value at the beginning of the frame and microframe represented by the <b>InputFrameNumber</b> and <b>InputMicroFrameNumber</b> input values.  




### -field QueryPerformanceCounterFrequency

The current performance-counter frequency, in counts per second.


### -field PredictedAccuracyInMicroSeconds

A value that represents the accuracy of the predicted QPC value in micro seconds. 




### -field CurrentGenerationID

An identifier for this request of time synchronization. 


### -field CurrentQueryPerformanceCounter

Current QPC value captured that is synchronized with the bus frame numbers represented by <b>CurrentHardwareFrameNumber</b>, <b>CurrentHardwareMicroFrameNumber</b> and <b>CurrentUSBFrameNumber</b>. 



 



### -field CurrentHardwareFrameNumber

A 1-bit value of the current hardware frame number that is directly read  from the MFINDEX register. 




### -field CurrentHardwareMicroFrameNumber

A 3-bit value of the current hardware micro frame number that is  directly read from the MFINDEX register. 




### -field CurrentUSBFrameNumber

A 32-bit USB frame number value returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_get_current_frame_number">_URB_GET_CURRENT_FRAME_NUMBER</a>.

