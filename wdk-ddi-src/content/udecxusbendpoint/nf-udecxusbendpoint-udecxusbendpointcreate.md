---
UID: NF:udecxusbendpoint.UdecxUsbEndpointCreate
title: UdecxUsbEndpointCreate function (udecxusbendpoint.h)
description: Creates a UDE endpoint object.
old-location: buses\udecxusbendpointcreate.htm
tech.root: usbref
ms.assetid: F97642A2-FE77-41D0-A194-8DE6F9B17BB0
ms.date: 05/07/2018
keywords: ["UdecxUsbEndpointCreate function"]
ms.keywords: UdecxUsbEndpointCreate, UdecxUsbEndpointCreate function [Buses], buses.udecxusbendpointcreate, udecxusbendpoint/UdecxUsbEndpointCreate
f1_keywords:
 - "udecxusbendpoint/UdecxUsbEndpointCreate"
 - "UdecxUsbEndpointCreate"
req.header: udecxusbendpoint.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Udecxstub.lib
- Udecxstub.dll
api_name:
- UdecxUsbEndpointCreate
targetos: Windows
req.typenames: 
---

# UdecxUsbEndpointCreate function


## -description


Creates a UDE endpoint object.


## -parameters




### -param EndpointInit

<p>A pointer to an <b>UDECXUSBENDPOINT_INIT</b> structure that the client driver retrieved in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate"><b>UdecxUsbSimpleEndpointInitAllocate</b></a>.</p>


### -param Attributes [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the USB device object. 


### -param UdecxUsbEndpoint [out]

A pointer to a variable that receives a handle to the new UDE endpoint object that represents the simple endpoint on the  USB device.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate">UdecxUsbSimpleEndpointInitAllocate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

