---
UID: NS:sti._STI_DEVICE_INFORMATIONW
title: "_STI_DEVICE_INFORMATIONW"
author: windows-driver-content
description: The STI_DEVICE_INFORMATION structure is used as an output parameter for the IStillImage::GetDeviceList and IStillImage::GetDeviceInfo functions. It is used as an input parameter for IStillImage::SetupDeviceParameters.
old-location: image\sti_device_information.htm
old-project: image
ms.assetid: 0c285630-876d-4b06-aace-4a2c4c06c1cb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: STI_DEVICE_INFORMATIONW, STI_DEVICE_INFORMATION, sti/PSTI_DEVICE_INFORMATION, PSTI_DEVICE_INFORMATION, *PSTI_DEVICE_INFORMATIONW, sti/STI_DEVICE_INFORMATIONW, PSTI_DEVICE_INFORMATION structure pointer [Imaging Devices], _STI_DEVICE_INFORMATIONW, stifnc_79a5d8d7-6b7a-4593-a8bf-05026d09e4a5.xml, STI_DEVICE_INFORMATION structure [Imaging Devices], image.sti_device_information
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	sti.h
apiname:
-	STI_DEVICE_INFORMATION
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_INFORMATIONW, *PSTI_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---

# _STI_DEVICE_INFORMATIONW structure


## -description


The STI_DEVICE_INFORMATION structure is used as an output parameter for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543784">IStillImage::GetDeviceList</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543782">IStillImage::GetDeviceInfo</a> functions. It is used as an input parameter for <a href="https://msdn.microsoft.com/library/windows/hardware/ff543803">IStillImage::SetupDeviceParameters</a>.


## -syntax


````
typedef struct _STI_DEVICE_INFORMATION {
  DWORD           dwSize;
  STI_DEVICE_TYPE DeviceType;
  TCHAR           szDeviceInternalName[STI_MAX_INTERNAL_NAME_LENGTH];
  STI_DEV_CAPS    DeviceCapabilities;
  DWORD           dwHardwareConfiguration;
  LPTSTR          pszVendorDescription;
  LPTSTR          pszDeviceDescription;
  LPTSTR          pszPortName;
  LPTSTR          pszPropProvider;
  LPTSTR          pszLocalName;
} STI_DEVICE_INFORMATION, *PSTI_DEVICE_INFORMATION;
````


## -struct-fields




### -field dwSize

Caller-supplied size, in bytes, of the STI_DEVICE_INFORMATION structure.


### -field DeviceType

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff548376">STI_DEVICE_TYPE</a>-typed value identifying the still image device type. 


### -field szDeviceInternalName

Character array containing the device's internal name string. The string can have at most STI_MAX_INTERNAL_NAME_LENGTH characters, including the terminating null character. STI_MAX_INTERNAL_NAME_LENGTH is defined in <i>Sti.h</i>.


### -field DeviceCapabilities

Structure of type <a href="..\sti\ns-sti-_sti_dev_caps.md">STI_DEV_CAPS</a>.


### -field dwHardwareConfiguration

Type of bus connection. The following constants are defined in <i>Sti.h</i>:

STI_HW_CONFIG_PARALLEL

STI_HW_CONFIG_SCSI

STI_HW_CONFIG_SERIAL

STI_HW_CONFIG_USB

STI_HW_CONFIG_UNKNOWN


### -field pszVendorDescription

Pointer to a vendor identification string, obtained from the <a href="https://msdn.microsoft.com/c5128d0a-d581-4461-8eb9-5680b6b6ef38">INF Manufacturer Section</a> of the device's INF file.


### -field pszDeviceDescription

Pointer to a device description string, obtained from the <a href="https://msdn.microsoft.com/b870e8fb-21b4-439b-b858-c45bf9be2ec1">INF Models Section</a> of the device's INF file.


### -field pszPortName

Pointer to a string identifying the device's port.


### -field pszPropProvider

Pointer to a string containing the file name and entry point of a DLL for adding device-specific property sheet pages to Control Panel. Obtained from the <b>PropertyPages</b> entry in the device's INF file.


### -field pszLocalName

Pointer to the local device name the user supplied during installation, for use in displays.

