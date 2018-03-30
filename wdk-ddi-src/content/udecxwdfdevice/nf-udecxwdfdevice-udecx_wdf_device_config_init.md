---
UID: NF:udecxwdfdevice.UDECX_WDF_DEVICE_CONFIG_INIT
title: UDECX_WDF_DEVICE_CONFIG_INIT function
author: windows-driver-content
description: Initializes a UDECX_WDF_DEVICE_CONFIG structure.
old-location: buses\udecx_wdf_device_config_init.htm
old-project: usbref
ms.assetid: EC26EDCA-1C9E-4D06-A970-71FB96FEB0DF
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UDECX_WDF_DEVICE_CONFIG_INIT, UDECX_WDF_DEVICE_CONFIG_INIT function [Buses], buses.udecx_wdf_device_config_init, udecxwdfdevice/UDECX_WDF_DEVICE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxwdfdevice.h
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UDECX_WDF_DEVICE_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: UDECX_WDF_DEVICE_RESET_ACTION, *PUDECX_WDF_DEVICE_RESET_ACTION
req.product: Windows 10 or later.
---

# UDECX_WDF_DEVICE_CONFIG_INIT function


## -description


Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt628008">UDECX_WDF_DEVICE_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt628008">UDECX_WDF_DEVICE_CONFIG</a> structure to initialize.


### -param EvtUdecxWdfDeviceQueryUsbCapability [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt595919">EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY</a> callback function.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt628008">UDECX_WDF_DEVICE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627990">UdecxWdfDeviceAddUsbDeviceEmulation</a>
 

 

