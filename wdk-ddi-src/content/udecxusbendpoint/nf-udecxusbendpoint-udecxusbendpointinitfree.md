---
UID: NF:udecxusbendpoint.UdecxUsbEndpointInitFree
title: UdecxUsbEndpointInitFree function (udecxusbendpoint.h)
description: Release the resources that were allocated by the UdecxUsbSimpleEndpointInitAllocate call.
old-location: buses\udecxusbendpointinitfree.htm
tech.root: usbref
ms.assetid: F95BDA95-4667-4EC3-9FE5-C78B453AC0B3
ms.date: 05/07/2018
ms.keywords: UdecxUsbEndpointInitFree, UdecxUsbEndpointInitFree function [Buses], buses.udecxusbendpointinitfree, udecxusbendpoint/UdecxUsbEndpointInitFree
ms.topic: function
f1_keywords:
 - "udecxusbendpoint/UdecxUsbEndpointInitFree"
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
- UdecxUsbEndpointInitFree
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbEndpointInitFree function


## -description


Release the resources that were allocated by the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate">UdecxUsbSimpleEndpointInitAllocate</a> call.


## -parameters




### -param Init [in]

A pointer to an <b>UDECXUSBENDPOINT_INIT</b> structure that the client driver retrieved in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate">UdecxUsbSimpleEndpointInitAllocate</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

