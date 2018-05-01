---
UID: NS:usbbusif._USBC_DEVICE_CONFIGURATION_INTERFACE_V1
title: "_USBC_DEVICE_CONFIGURATION_INTERFACE_V1"
author: windows-driver-content
description: The USBC_DEVICE_CONFIGURATION_INTERFACE_V1 structure is exposed by the vendor-supplied filter drivers to assist the USB generic parent driver in defining interface collections.
old-location: buses\usbc_device_configuration_interface_v1.htm
old-project: usbref
ms.assetid: 86e8946f-f87f-40d4-bd02-6e4befe847e0
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PUSBC_DEVICE_CONFIGURATION_INTERFACE_V1, PUSBC_DEVICE_CONFIGURATION_INTERFACE_V1, PUSBC_DEVICE_CONFIGURATION_INTERFACE_V1 structure pointer [Buses], USBC_DEVICE_CONFIGURATION_INTERFACE_V1, USBC_DEVICE_CONFIGURATION_INTERFACE_V1 structure [Buses], _USBC_DEVICE_CONFIGURATION_INTERFACE_V1, buses.usbc_device_configuration_interface_v1, usbbusif/PUSBC_DEVICE_CONFIGURATION_INTERFACE_V1, usbbusif/USBC_DEVICE_CONFIGURATION_INTERFACE_V1, usbinterKR_f3f8ee06-a861-4787-a611-766308347395.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbbusif.h
req.include-header: Usbbusif.h
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
-	usbbusif.h
api_name:
-	USBC_DEVICE_CONFIGURATION_INTERFACE_V1
product: Windows
targetos: Windows
req.typenames: USBC_DEVICE_CONFIGURATION_INTERFACE_V1, *PUSBC_DEVICE_CONFIGURATION_INTERFACE_V1
---

# _USBC_DEVICE_CONFIGURATION_INTERFACE_V1 structure


## -description


The <b>USBC_DEVICE_CONFIGURATION_INTERFACE_V1</b> structure is exposed by the vendor-supplied filter drivers to assist the USB generic parent driver in defining interface collections.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The version of the interface.


### -field Context

The USB generic parent driver does not use this member. It is populated by the vendor supplied filter driver and may be used to track instance information for the bus interface. It is passed as a parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a>. 


### -field InterfaceReference

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a>. 


### -field InterfaceDereference

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a>. 


### -field StartDeviceCallback

Pointer to the callback routine that the filter driver furnishes to the USB generic parent driver to assist in defining interface collections on a device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539007">USBC_START_DEVICE_CALLBACK</a>.


### -field PdoEnableCallback

Reserved.


### -field Reserved

Reserved.


## -see-also




<a href="https://msdn.microsoft.com/3cf4e9f2-ea33-491f-94af-62d2afacc899">Customizing Enumeration of Interface Collections for Composite Devices</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539007">USBC_START_DEVICE_CALLBACK</a>
 

 

