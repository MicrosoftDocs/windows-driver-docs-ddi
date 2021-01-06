---
UID: NS:dispmprt._DXGK_DEVICE_INFO
title: _DXGK_DEVICE_INFO (dispmprt.h)
description: The DXGK_DEVICE_INFO structure holds information that describes a display adapter.
old-location: display\dxgk_device_info.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGK_DEVICE_INFO structure"]
ms.keywords: "*PDXGK_DEVICE_INFO, DXGK_DEVICE_INFO, DXGK_DEVICE_INFO structure [Display Devices], DmStructs_89344ee9-8c4e-4f7e-8950-11948c07bb8e.xml, PDXGK_DEVICE_INFO, PDXGK_DEVICE_INFO structure pointer [Display Devices], _DXGK_DEVICE_INFO, display.dxgk_device_info, dispmprt/DXGK_DEVICE_INFO, dispmprt/PDXGK_DEVICE_INFO"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: DXGK_DEVICE_INFO, *PDXGK_DEVICE_INFO
f1_keywords:
 - _DXGK_DEVICE_INFO
 - dispmprt/_DXGK_DEVICE_INFO
 - PDXGK_DEVICE_INFO
 - dispmprt/PDXGK_DEVICE_INFO
 - DXGK_DEVICE_INFO
 - dispmprt/DXGK_DEVICE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - DXGK_DEVICE_INFO
---

# _DXGK_DEVICE_INFO structure


## -description

The DXGK_DEVICE_INFO structure holds information that describes a display adapter.

## -struct-fields

### -field MiniportDeviceContext

A handle to a context block (created and maintained by the display miniport driver) associated with a display adapter.

### -field PhysicalDeviceObject

A pointer to the physical device object (PDO) that represents the display adapter.

### -field DeviceRegistryPath

A Unicode string that holds the registry path of the software key for the display adapter. Registry data should be written only to this path.

### -field TranslatedResourceList

A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a> structure that holds the translated resources assigned to the display adapter.

### -field SystemMemorySize

The size, in bytes, of system memory.

### -field HighestPhysicalAddress

The highest physical address of system memory (RAM).

### -field AgpApertureBase

The base physical address of the AGP aperture. If 0, the display adapter is not an AGP adapter, or AGP resources were not found.

### -field AgpApertureSize

The size, in bytes, of the AGP aperture. If 0, the display adapter is not an AGP adapter, or AGP resources were not found.

### -field DockingState

The state of a portable computer that can be attached to a docking station.

## -remarks

The display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function allocates a DXGK_DEVICE_INFO structure and calls <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_get_device_information">DxgkCbGetDeviceInformation</a> to get that structure filled in with information about a display adapter. Five of the structure members (<b>Version</b>, <b>SystemMemorySize</b>, <b>HighestPhysicalAddress</b>, <b>AgpApertureBase</b>, and <b>AgpApertureSize</b>) hold general information and are not associated with a particular display adapter. Those members are included in the DXGK_DEVICE_INFO structure because they provide information that <i>DxgkDdiStartDevice</i> requires to initialize the driver and display adapter hardware.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_get_device_information">DxgkCbGetDeviceInformation</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>
