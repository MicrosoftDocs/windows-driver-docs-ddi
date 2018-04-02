---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
title: EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
author: windows-driver-content
description: UCX invokes this callback to retrieves the system query performance counter (QPC) value synchronized with the frame and microframe.
old-location: buses\evt_ucx_controller_get_frame_number_and_qpc_for_time_sync.htm
old-project: usbref
ms.assetid: A8D666BD-5C2A-416F-901E-5FF7CF38A084
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC, EvtUcxControllerGetFrameNumberAndQpcForTimeSync, EvtUcxControllerGetFrameNumberAndQpcForTimeSync callback function [Buses], buses.evt_ucx_controller_get_frame_number_and_qpc_for_time_sync, ucxcontroller/EvtUcxControllerGetFrameNumberAndQpcForTimeSync
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
-	EvtUcxControllerGetFrameNumberAndQpcForTimeSync
product: Windows
targetos: Windows
req.typenames: UCM_PD_REQUEST_DATA_OBJECT, *PUCM_PD_REQUEST_DATA_OBJECT
req.product: Windows 10 or later.
---

# EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC callback


## -description


UCX invokes this callback to retrieves the system query performance counter (QPC) value  synchronized with the  frame and microframe.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param WdfRequest [in]

A framework request object that contains the request to get the synchronized frame and microframe number.


### -param OutputBufferLength [in]

The length, in bytes, of the request's output buffer, if an output buffer
        is available. This value is the size of the <a href="https://msdn.microsoft.com/F602B738-4D04-4A75-BE69-CFEC4F76904C">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a> structure. 


### -param InputBufferLength [in]

The length, in bytes, of the request's input buffer, if an input buffer
        is available. This value is the size of the <a href="https://msdn.microsoft.com/F602B738-4D04-4A75-BE69-CFEC4F76904C">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a> structure.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/701A7ED2-F35F-4B6B-BC91-ADCF60E294D2">IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC</a>
 

 

