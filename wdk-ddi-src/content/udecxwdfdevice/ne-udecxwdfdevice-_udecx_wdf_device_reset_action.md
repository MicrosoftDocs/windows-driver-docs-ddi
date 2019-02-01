---
UID: NE:udecxwdfdevice._UDECX_WDF_DEVICE_RESET_ACTION
title: _UDECX_WDF_DEVICE_RESET_ACTION (udecxwdfdevice.h)
description: Defines values that indicate the types of reset operation supported by an emulated USB host controller.
old-location: buses\udecx_wdf_device_reset_action.htm
tech.root: usbref
ms.assetid: E3216F62-5506-4DA2-AD89-B2406D3E97C0
ms.date: 05/07/2018
ms.keywords: "*PUDECX_WDF_DEVICE_RESET_ACTION, UDECX_WDF_DEVICE_RESET_ACTION, UDECX_WDF_DEVICE_RESET_ACTION enumeration [Buses], UdecxWdfDeviceResetActionResetEachUsbDevice, UdecxWdfDeviceResetActionResetWdfDevice, _UDECX_WDF_DEVICE_RESET_ACTION, buses.udecx_wdf_device_reset_action, udecxwdfdevice/UDECX_WDF_DEVICE_RESET_ACTION, udecxwdfdevice/UdecxWdfDeviceResetActionResetEachUsbDevice, udecxwdfdevice/UdecxWdfDeviceResetActionResetWdfDevice"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UdecxWdfDevice.h
api_name:
-	UDECX_WDF_DEVICE_RESET_ACTION
product:
- Windows
targetos: Windows
req.typenames: UDECX_WDF_DEVICE_RESET_ACTION, *PUDECX_WDF_DEVICE_RESET_ACTION
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
 

 

