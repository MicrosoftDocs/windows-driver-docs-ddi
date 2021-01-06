---
UID: NS:wdm._CM_SERIAL_DEVICE_DATA
title: _CM_SERIAL_DEVICE_DATA (wdm.h)
description: The CM_SERIAL_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a serial controller if the system can collect this information during the boot process.
old-location: kernel\cm_serial_device_data.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["CM_SERIAL_DEVICE_DATA structure"]
ms.keywords: "*PCM_SERIAL_DEVICE_DATA, CM_SERIAL_DEVICE_DATA, CM_SERIAL_DEVICE_DATA structure [Kernel-Mode Driver Architecture], PCM_SERIAL_DEVICE_DATA, PCM_SERIAL_DEVICE_DATA structure pointer [Kernel-Mode Driver Architecture], _CM_SERIAL_DEVICE_DATA, kernel.cm_serial_device_data, kstruct_a_5b9a8153-d673-4576-b861-3242faf23c54.xml, wdm/CM_SERIAL_DEVICE_DATA, wdm/PCM_SERIAL_DEVICE_DATA"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.typenames: CM_SERIAL_DEVICE_DATA, *PCM_SERIAL_DEVICE_DATA
f1_keywords:
 - _CM_SERIAL_DEVICE_DATA
 - wdm/_CM_SERIAL_DEVICE_DATA
 - PCM_SERIAL_DEVICE_DATA
 - wdm/PCM_SERIAL_DEVICE_DATA
 - CM_SERIAL_DEVICE_DATA
 - wdm/CM_SERIAL_DEVICE_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - CM_SERIAL_DEVICE_DATA
---

# _CM_SERIAL_DEVICE_DATA structure


## -description

The <b>CM_SERIAL_DEVICE_DATA</b> structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a serial controller if the system can collect this information during the boot process.

## -struct-fields

### -field Version

The version number of this structure.

### -field Revision

The revision of this structure.

### -field BaudClock

The clock baud rate, in megahertz, at which data is transferred.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/kernel/mmcreatemdl">IoQueryDeviceDescription</a>



<a href="/windows-hardware/drivers/kernel/mmcreatemdl">IoReportResourceUsage</a>
