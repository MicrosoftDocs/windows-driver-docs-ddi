---
UID: NI:usbioctl.IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
title: IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
description: "."
old-location: buses\_ioctl_usb_get_frame_number_and_qpc_for_time_sync.htm
tech.root: usbref
ms.assetid: 701A7ED2-F35F-4B6B-BC91-ADCF60E294D2
ms.date: 05/07/2018
ms.keywords: IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC, IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC control, IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC control code [Buses], buses._ioctl_usb_get_frame_number_and_qpc_for_time_sync, usbioctl/ IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC IOCTL


## -description


Retrieves the system query performance counter (QPC) value  synchronized with the  frame and microframe.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer

A pointer to a <a href="https://msdn.microsoft.com/F602B738-4D04-4A75-BE69-CFEC4F76904C">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a> structure that contains the time tracking handled retrieved by  the <a href="https://msdn.microsoft.com/C9EA7A04-3B53-46D4-BC1B-A2766577095F">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a> request.  On input, the caller can specify a frame and microframe number for which to retrieve the QPC value.

On output, the <b>CurrentQueryPerformanceCounter</b> member is set to a value predicted by the USB driver stack. The value represents the system QPC value in microseconds.


### -inout-buffer-length

The size of the <a href="https://msdn.microsoft.com/F602B738-4D04-4A75-BE69-CFEC4F76904C">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a> structure.


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates an the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



On input, the caller can optionally specify a frame and microframe for which the caller is interested in knowing the associated system QPC value. Those values must be provided in the <b>InputFrameNumber</b> and <b>InputMicroFrameNumber</b> members of <a href="https://msdn.microsoft.com/F602B738-4D04-4A75-BE69-CFEC4F76904C">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a>, respectively. On output, the USB driver stack fills the <b>QueryPerformanceCounterAtInputFrameOrMicroFrame</b> member  with a system QPC value calculated by the USB driver stack.

If the caller is not interested those values, <b>InputFrameNumber</b> and <b>InputMicroFrameNumber</b> values must be initialized to 0. On output, <b>QueryPerformanceCounterAtInputFrameOrMicroFrame</b>  is set to 0.

 If the USB driver stack encountered a frame boundary, the <b>PredictedAccuracyInMicroSeconds</b> value indicates accuracy in 125-microseconds unit. It also takes into consideration if sufficient time has elapsed since tracking is enabled. 



 



The USB driver stack can also predict the system QPC value that are synchronized with bus frame and microframe numbers retrieved directly from the host controller. 

In order to predict QPC  values with accuracy, the USB driver stack might poll the frame and microframe time sources. That polling operation might require raising or lowering of IRQL to eliminate scheduling delays interfering with the accuracy of the value (after attempting to read the register/QPC timer from passive IRQL for a given number of tries). Given this possible additional CPU cost, this interface must only be used to get associated USB bus and QPC values and must not be used as a replacement to existing methods for retrieving just the USB bus time. 





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

