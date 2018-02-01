---
UID: NF:udecxwdfdevice.UDECX_WDF_DEVICE_CONFIG_INIT
title: UDECX_WDF_DEVICE_CONFIG_INIT function
author: windows-driver-content
description: Initializes a UDECX_WDF_DEVICE_CONFIG structure.
old-location: buses\udecx_wdf_device_config_init.htm
old-project: usbref
ms.assetid: EC26EDCA-1C9E-4D06-A970-71FB96FEB0DF
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: udecxwdfdevice/UDECX_WDF_DEVICE_CONFIG_INIT, buses.udecx_wdf_device_config_init, UDECX_WDF_DEVICE_CONFIG_INIT function [Buses], UDECX_WDF_DEVICE_CONFIG_INIT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Udecxstub.lib
-	Udecxstub.dll
apiname:
-	UDECX_WDF_DEVICE_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: "*PUDECX_WDF_DEVICE_RESET_ACTION, UDECX_WDF_DEVICE_RESET_ACTION"
req.product: Windows 10 or later.
---

# UDECX_WDF_DEVICE_CONFIG_INIT function


## -description


Initializes a <a href="..\udecxwdfdevice\ns-udecxwdfdevice-_udecx_wdf_device_config.md">UDECX_WDF_DEVICE_CONFIG</a> structure.


## -syntax


````
FORCEINLINE void UDECX_WDF_DEVICE_CONFIG_INIT(
  _Out_ PUDECX_WDF_DEVICE_CONFIG                  Config,
  _In_  PFN_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY EvtUdecxWdfDeviceQueryUsbCapability
);
````


## -parameters




### -param Config [out]

A pointer to a <a href="..\udecxwdfdevice\ns-udecxwdfdevice-_udecx_wdf_device_config.md">UDECX_WDF_DEVICE_CONFIG</a> structure to initialize.


### -param EvtUdecxWdfDeviceQueryUsbCapability [in]

A pointer to an <a href="..\udecxwdfdevice\nc-udecxwdfdevice-evt_udecx_wdf_device_query_usb_capability.md">EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY</a> callback function.


## -returns


This function does not return a value.



## -see-also

<a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md">UdecxWdfDeviceAddUsbDeviceEmulation</a>

<a href="..\udecxwdfdevice\ns-udecxwdfdevice-_udecx_wdf_device_config.md">UDECX_WDF_DEVICE_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_WDF_DEVICE_CONFIG_INIT function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

