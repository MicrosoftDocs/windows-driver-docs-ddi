---
UID: NS:sti._STI_DEVICE_INFORMATIONW
title: _STI_DEVICE_INFORMATIONW (sti.h)
description: The STI_DEVICE_INFORMATION structure is used as an output parameter for the IStillImage::GetDeviceList and IStillImage::GetDeviceInfo functions. It is used as an input parameter for IStillImage::SetupDeviceParameters.
old-location: image\sti_device_information.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["STI_DEVICE_INFORMATIONW structure"]
ms.keywords: "*PSTI_DEVICE_INFORMATIONW, PSTI_DEVICE_INFORMATION, PSTI_DEVICE_INFORMATION structure pointer [Imaging Devices], STI_DEVICE_INFORMATION, STI_DEVICE_INFORMATION structure [Imaging Devices], STI_DEVICE_INFORMATIONW, _STI_DEVICE_INFORMATIONW, image.sti_device_information, sti/PSTI_DEVICE_INFORMATION, sti/STI_DEVICE_INFORMATIONW, stifnc_79a5d8d7-6b7a-4593-a8bf-05026d09e4a5.xml"
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
targetos: Windows
req.typenames: STI_DEVICE_INFORMATIONW, *PSTI_DEVICE_INFORMATIONW
f1_keywords:
 - _STI_DEVICE_INFORMATIONW
 - sti/_STI_DEVICE_INFORMATIONW
 - PSTI_DEVICE_INFORMATIONW
 - sti/PSTI_DEVICE_INFORMATIONW
 - STI_DEVICE_INFORMATIONW
 - sti/STI_DEVICE_INFORMATIONW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - sti.h
api_name:
 - _STI_DEVICE_INFORMATIONW
 - PSTI_DEVICE_INFORMATIONW
 - STI_DEVICE_INFORMATIONW
---

# _STI_DEVICE_INFORMATIONW structure


## -description

The STI_DEVICE_INFORMATION structure is used as an output parameter for the <a href="/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)">IStillImage::GetDeviceList</a> and <a href="/previous-versions/windows/hardware/drivers/ff543782(v=vs.85)">IStillImage::GetDeviceInfo</a> functions. It is used as an input parameter for <a href="/previous-versions/windows/hardware/drivers/ff543803(v=vs.85)">IStillImage::SetupDeviceParameters</a>.

## -struct-fields

### -field dwSize

Caller-supplied size, in bytes, of the STI_DEVICE_INFORMATION structure.

### -field DeviceType

An <a href="/windows-hardware/drivers/ddi/sti/ne-sti-_sti_device_mj_type">STI_DEVICE_TYPE</a>-typed value identifying the still image device type.

### -field szDeviceInternalName

Character array containing the device's internal name string. The string can have at most STI_MAX_INTERNAL_NAME_LENGTH characters, including the terminating null character. STI_MAX_INTERNAL_NAME_LENGTH is defined in <i>Sti.h</i>.

### -field DeviceCapabilities

Structure of type <a href="/windows-hardware/drivers/ddi/sti/ns-sti-_sti_dev_caps">STI_DEV_CAPS</a>.

### -field dwHardwareConfiguration

Type of bus connection. The following constants are defined in <i>Sti.h</i>:

STI_HW_CONFIG_PARALLEL

STI_HW_CONFIG_SCSI

STI_HW_CONFIG_SERIAL

STI_HW_CONFIG_USB

STI_HW_CONFIG_UNKNOWN

### -field pszVendorDescription

Pointer to a vendor identification string, obtained from the <a href="/windows-hardware/drivers/install/inf-manufacturer-section">INF Manufacturer Section</a> of the device's INF file.

### -field pszDeviceDescription

Pointer to a device description string, obtained from the <a href="/windows-hardware/drivers/install/inf-models-section">INF Models Section</a> of the device's INF file.

### -field pszPortName

Pointer to a string identifying the device's port.

### -field pszPropProvider

Pointer to a string containing the file name and entry point of a DLL for adding device-specific property sheet pages to Control Panel. Obtained from the <b>PropertyPages</b> entry in the device's INF file.

### -field pszLocalName

Pointer to the local device name the user supplied during installation, for use in displays.

