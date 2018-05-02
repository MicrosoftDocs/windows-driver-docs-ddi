---
UID: NS:sti._STI_WIA_DEVICE_INFORMATIONW
title: "_STI_WIA_DEVICE_INFORMATIONW"
author: windows-driver-content
description: The STI_WIA_DEVICE_INFORMATION structure contains device information.
old-location: image\sti_wia_device_information.htm
old-project: image
ms.assetid: a1339fd5-49ec-498b-bc07-221526a57d74
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PSTI_WIA_DEVICE_INFORMATIONW, PSTI_WIA_DEVICE_INFORMATION, PSTI_WIA_DEVICE_INFORMATION structure pointer [Imaging Devices], STI_WIA_DEVICE_INFORMATION, STI_WIA_DEVICE_INFORMATION structure [Imaging Devices], STI_WIA_DEVICE_INFORMATIONW, _STI_WIA_DEVICE_INFORMATIONW, image.sti_wia_device_information, sti/PSTI_WIA_DEVICE_INFORMATION, sti/STI_WIA_DEVICE_INFORMATION, stifnc_5b853150-0ce1-4ba1-bf9c-2071c6a993bc.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sti.h
req.include-header: Sti.h
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
-	sti.h
api_name:
-	STI_WIA_DEVICE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
---

# _STI_WIA_DEVICE_INFORMATIONW structure


## -description


The STI_WIA_DEVICE_INFORMATION structure contains device information.


## -struct-fields




### -field dwSize

Caller-supplied size, in bytes, of the STI_WIA_DEVICE_INFORMATION structure. 


### -field DeviceType

A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff548376">STI_DEVICE_TYPE</a> that identifies the type of the hardware imaging device.


### -field szDeviceInternalName

Character array containing the device's internal name string, used for reference when the device object is created. The string can have at most STI_MAX_INTERNAL_NAME_LENGTH characters, including the terminating null character. STI_MAX_INTERNAL_NAME_LENGTH is defined in <i>Sti.h</i>.


### -field DeviceCapabilities

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff548380">STI_DEV_CAPS</a>.


### -field dwHardwareConfiguration

Type of bus connection. This value can be one of the following constants, which are defined in <i>Sti.h</i>: 

STI_HW_CONFIG_PARALLEL 

STI_HW_CONFIG_SCSI

STI_HW_CONFIG_SERIAL

STI_HW_CONFIG_USB

STI_HW_CONFIG_UNKNOWN


### -field pszVendorDescription

Pointer to a vendor identification string, obtained from the <a href="https://msdn.microsoft.com/c5128d0a-d581-4461-8eb9-5680b6b6ef38">INF Manufacturer Section</a> of the device's INF file. 


### -field pszDeviceDescription

Pointer to a vendor-provided device description string, obtained from the <a href="https://msdn.microsoft.com/b870e8fb-21b4-439b-b858-c45bf9be2ec1">INF Models Section</a> of the device's INF file.


### -field pszPortName

Pointer to a string identifying the device's port.


### -field pszPropProvider

Pointer to a string containing the file name and entry point of a DLL for adding device-specific property sheet pages to Control Panel. Obtained from the <b>PropertyPages</b> entry in the device's INF file. 


### -field pszLocalName

Pointer to a string containing the local device name (the "friendly" name). The user supplies this string during installation, typically for use in user interface displays.


### -field pszUiDll

Pointer to the WIA user interface DLL.


### -field pszServer

Pointer to the WIA server.

