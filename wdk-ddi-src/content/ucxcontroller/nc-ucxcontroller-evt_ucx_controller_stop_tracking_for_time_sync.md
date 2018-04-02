---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_STOP_TRACKING_FOR_TIME_SYNC
title: EVT_UCX_CONTROLLER_STOP_TRACKING_FOR_TIME_SYNC
author: windows-driver-content
description: UCX invokes this callback function to the stop time tracking functionality in the controller.
old-location: buses\evt_ucx_controller_stop_tracking_for_time_sync.htm
old-project: usbref
ms.assetid: C65A250A-594B-4317-AEE6-C3E60D122A1D
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EVT_UCX_CONTROLLER_STOP_TRACKING_FOR_TIME_SYNC, EvUcxControllerStopTrackingForTimeSync, EvUcxControllerStopTrackingForTimeSync callback function [Buses], buses.evt_ucx_controller_stop_tracking_for_time_sync, ucxcontroller/EvUcxControllerStopTrackingForTimeSync
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ucxcontroller.h
api_name:
-	EvUcxControllerStopTrackingForTimeSync
product: Windows
targetos: Windows
req.typenames: UCM_PD_REQUEST_DATA_OBJECT, *PUCM_PD_REQUEST_DATA_OBJECT
req.product: Windows 10 or later.
---

# EVT_UCX_CONTROLLER_STOP_TRACKING_FOR_TIME_SYNC callback


## -description


UCX invokes this callback function to the stop  time tracking functionality in the controller. 


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param WdfRequest [in]

A framework request object that contains the request to stop time tracking.


### -param OutputBufferLength [in]

The length, in bytes, of the request's output buffer, if an output buffer
        is available. This value is the size of the <a href="https://msdn.microsoft.com/FFD7979B-48E9-433C-86A9-255F4F422BBA">USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure. 


### -param InputBufferLength [in]

The length, in bytes, of the request's input buffer, if an input buffer
        is available. This value is the size of the <a href="https://msdn.microsoft.com/FFD7979B-48E9-433C-86A9-255F4F422BBA">USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/232AC14B-CE3C-44AC-9428-5594993CD749">IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC</a>
 

 

