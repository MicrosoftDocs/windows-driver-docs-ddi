---
UID: NI:usbioctl.IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
title: IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
author: windows-driver-content
description: "."
old-location: buses\_ioctl_usb_get_frame_number_and_qpc_for_time_sync.htm
old-project: UsbRef
ms.assetid: 701A7ED2-F35F-4B6B-BC91-ADCF60E294D2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: buses._ioctl_usb_get_frame_number_and_qpc_for_time_sync, IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC control code [Buses], IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC, usbioctl/ IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC IOCTL


##  Major Code: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


Retrieves the system query performance counter (QPC) value  synchronized with the  frame and microframe.


## -ioctlparameters




### -input-buffer



<text></text>




### -input-buffer-length



<text></text>




### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer

A pointer to a <a href="..\usbioctl\ns-usbioctl-_usb_frame_number_and_qpc_for_time_sync_information.md">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a> structure that contains the time tracking handled retrieved by  the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_start_tracking_for_time_sync.md">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a> request.  On input, the caller can specify a frame and microframe number for which to retrieve the QPC value.

On output, the <b>CurrentQueryPerformanceCounter</b> member is set to a value predicted by the USB driver stack. The value represents the system QPC value in microseconds.


### -inout-buffer-length

The size of the <a href="..\usbioctl\ns-usbioctl-_usb_frame_number_and_qpc_for_time_sync_information.md">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a> structure.


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates an the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



On input, the caller can optionally specify a frame and microframe for which the caller is interested in knowing the associated system QPC value. Those values must be provided in the <b>InputFrameNumber</b> and <b>InputMicroFrameNumber</b> members of <a href="..\usbioctl\ns-usbioctl-_usb_frame_number_and_qpc_for_time_sync_information.md">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a>, respectively. On output, the USB driver stack fills the <b>QueryPerformanceCounterAtInputFrameOrMicroFrame</b> member  with a system QPC value calculated by the USB driver stack.

If the caller is not interested those values, <b>InputFrameNumber</b> and <b>InputMicroFrameNumber</b> values must be initialized to 0. On output, <b>QueryPerformanceCounterAtInputFrameOrMicroFrame</b>  is set to 0.

 If the USB driver stack encountered a frame boundary, the <b>PredictedAccuracyInMicroSeconds</b> value indicates accuracy in 125-microseconds unit. It also takes into consideration if sufficient time has elapsed since tracking is enabled. 



 



The USB driver stack can also predict the system QPC value that are synchronized with bus frame and microframe numbers retrieved directly from the host controller. 

In order to predict QPC  values with accuracy, the USB driver stack might poll the frame and microframe time sources. That polling operation might require raising or lowering of IRQL to eliminate scheduling delays interfering with the accuracy of the value (after attempting to read the register/QPC timer from passive IRQL for a given number of tries). Given this possible additional CPU cost, this interface must only be used to get associated USB bus and QPC values and must not be used as a replacement to existing methods for retrieving just the USB bus time. 





## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20 IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

