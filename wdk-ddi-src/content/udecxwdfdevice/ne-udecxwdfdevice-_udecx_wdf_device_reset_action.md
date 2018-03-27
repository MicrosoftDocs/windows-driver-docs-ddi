---
UID: NE:udecxwdfdevice._UDECX_WDF_DEVICE_RESET_ACTION
title: "_UDECX_WDF_DEVICE_RESET_ACTION"
author: windows-driver-content
description: Defines values that indicate the types of reset operation supported by an emulated USB host controller.
old-location: buses\udecx_wdf_device_reset_action.htm
old-project: usbref
ms.assetid: E3216F62-5506-4DA2-AD89-B2406D3E97C0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUDECX_WDF_DEVICE_RESET_ACTION, UDECX_WDF_DEVICE_RESET_ACTION, UDECX_WDF_DEVICE_RESET_ACTION enumeration [Buses], UdecxWdfDeviceResetActionResetEachUsbDevice, UdecxWdfDeviceResetActionResetWdfDevice, _UDECX_WDF_DEVICE_RESET_ACTION, buses.udecx_wdf_device_reset_action, udecxwdfdevice/UDECX_WDF_DEVICE_RESET_ACTION, udecxwdfdevice/UdecxWdfDeviceResetActionResetEachUsbDevice, udecxwdfdevice/UdecxWdfDeviceResetActionResetWdfDevice"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: udecxwdfdevice.h
req.include-header: Udecx.h
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UdecxWdfDevice.h
api_name:
-	UDECX_WDF_DEVICE_RESET_ACTION
product: Windows
targetos: Windows
req.typenames: UDECX_WDF_DEVICE_RESET_ACTION, *PUDECX_WDF_DEVICE_RESET_ACTION
req.product: Windows 10 or later.
---

# _UDECX_WDF_DEVICE_RESET_ACTION enumeration


## -description


Defines values that indicate the types of reset operation supported by an emulated USB host controller.


## -enum-fields




### -field UdecxWdfDeviceResetActionResetEachUsbDevice

Each device that is attached to the controller is reset.


### -field UdecxWdfDeviceResetActionResetWdfDevice

The emulated host controller is reset.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595920">EVT_UDECX_WDF_DEVICE_RESET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt628008">UDECX_WDF_DEVICE_CONFIG</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_WDF_DEVICE_RESET_ACTION enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

