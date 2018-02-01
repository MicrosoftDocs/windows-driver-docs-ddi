---
UID: NE:wdm._DEVICE_RESET_TYPE
title: "_DEVICE_RESET_TYPE"
author: windows-driver-content
description: The DEVICE_RESET_TYPE enumeration specifies the type of device reset that is being requested by a call to the DeviceReset routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface.
old-location: kernel\device_reset_type.htm
old-project: kernel
ms.assetid: 598044D9-8B99-453C-96FE-9B04C980BB3A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/DEVICE_RESET_TYPE, DEVICE_RESET_TYPE, wdm/FunctionLevelDeviceReset, PlatformLevelDeviceReset, DEVICE_RESET_TYPE enumeration [Kernel-Mode Driver Architecture], FunctionLevelDeviceReset, wdm/PlatformLevelDeviceReset, kernel.device_reset_type, _DEVICE_RESET_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	DEVICE_RESET_TYPE
product: Windows
targetos: Windows
req.typenames: DEVICE_RESET_TYPE
req.product: Windows 10 or later.
---

# _DEVICE_RESET_TYPE enumeration


## -description


The <b>DEVICE_RESET_TYPE</b> enumeration specifies the type of device reset that is being requested by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939354">DeviceReset</a> routine of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn928420">GUID_DEVICE_RESET_INTERFACE_STANDARD</a> interface.


## -syntax


````
typedef enum _DEVICE_RESET_TYPE { 
  FunctionLevelDeviceReset  = 0,
  PlatformLevelDeviceReset  = 1
} DEVICE_RESET_TYPE;
````


## -enum-fields




### -field FunctionLevelDeviceReset

A function-level device reset, which is restricted to a specific device.


### -field PlatformLevelDeviceReset

A platform-level device reset, which affects a specific device and all other devices that are connected to it via the same power rail or reset line.


## -see-also

<a href="..\wdm\ns-wdm-_device_reset_interface_standard.md">DEVICE_RESET_INTERFACE_STANDARD</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn939354">DeviceReset</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn928420">GUID_DEVICE_RESET_INTERFACE_STANDARD</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DEVICE_RESET_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

