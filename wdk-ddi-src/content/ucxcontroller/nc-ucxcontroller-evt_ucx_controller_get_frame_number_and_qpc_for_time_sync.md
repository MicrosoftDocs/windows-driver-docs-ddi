---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
title: EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC (ucxcontroller.h)
description: UCX invokes this callback to retrieves the system query performance counter (QPC) value synchronized with the frame and microframe.
old-location: buses\evt_ucx_controller_get_frame_number_and_qpc_for_time_sync.htm
tech.root: usbref
ms.assetid: A8D666BD-5C2A-416F-901E-5FF7CF38A084
ms.date: 05/07/2018
ms.keywords: EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC, EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC callback, EvtUcxControllerGetFrameNumberAndQpcForTimeSync, EvtUcxControllerGetFrameNumberAndQpcForTimeSync callback function [Buses], buses.evt_ucx_controller_get_frame_number_and_qpc_for_time_sync, ucxcontroller/EvtUcxControllerGetFrameNumberAndQpcForTimeSync
ms.topic: callback
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ucxcontroller.h
api_name:
- EvtUcxControllerGetFrameNumberAndQpcForTimeSync
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC callback function


## -description


UCX invokes this callback to retrieves the system query performance counter (QPC) value  synchronized with the  frame and microframe.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param WdfRequest [in]

A framework request object that contains the request to get the synchronized frame and microframe number.


### -param OutputBufferLength [in]

The length, in bytes, of the request's output buffer, if an output buffer
        is available. This value is the size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ns-usbioctl-_usb_frame_number_and_qpc_for_time_sync_information">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a> structure. 


### -param InputBufferLength [in]

The length, in bytes, of the request's input buffer, if an input buffer
        is available. This value is the size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ns-usbioctl-_usb_frame_number_and_qpc_for_time_sync_information">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a> structure.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ni-usbioctl-ioctl_usb_get_frame_number_and_qpc_for_time_sync">IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC</a>
 

 

