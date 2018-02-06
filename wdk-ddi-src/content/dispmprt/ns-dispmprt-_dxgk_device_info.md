---
UID: NS:dispmprt._DXGK_DEVICE_INFO
title: "_DXGK_DEVICE_INFO"
author: windows-driver-content
description: The DXGK_DEVICE_INFO structure holds information that describes a display adapter.
old-location: display\dxgk_device_info.htm
old-project: display
ms.assetid: dcdae08f-69a6-496b-8391-d2b505fb86d9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: dispmprt/PDXGK_DEVICE_INFO, dispmprt/DXGK_DEVICE_INFO, *PDXGK_DEVICE_INFO, PDXGK_DEVICE_INFO, display.dxgk_device_info, DmStructs_89344ee9-8c4e-4f7e-8950-11948c07bb8e.xml, _DXGK_DEVICE_INFO, DXGK_DEVICE_INFO, DXGK_DEVICE_INFO structure [Display Devices], PDXGK_DEVICE_INFO structure pointer [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dispmprt.h
apiname:
-	DXGK_DEVICE_INFO
product: Windows
targetos: Windows
req.typenames: "*PDXGK_DEVICE_INFO, DXGK_DEVICE_INFO"
---

# _DXGK_DEVICE_INFO structure


## -description


The DXGK_DEVICE_INFO structure holds information that describes a display adapter.


## -syntax


````
typedef struct _DXGK_DEVICE_INFO {
  PVOID             MiniportDeviceContext;
  PDEVICE_OBJECT    PhysicalDeviceObject;
  UNICODE_STRING    DeviceRegistryPath;
  PCM_RESOURCE_LIST TranslatedResourceList;
  LARGE_INTEGER     SystemMemorySize;
  PHYSICAL_ADDRESS  HighestPhysicalAddress;
  PHYSICAL_ADDRESS  AgpApertureBase;
  SIZE_T            AgpApertureSize;
  DOCKING_STATE     DockingState;
} DXGK_DEVICE_INFO, *PDXGK_DEVICE_INFO;
````


## -struct-fields




### -field MiniportDeviceContext

A handle to a context block (created and maintained by the display miniport driver) associated with a display adapter.


### -field PhysicalDeviceObject

A pointer to the physical device object (PDO) that represents the display adapter.


### -field DeviceRegistryPath

A Unicode string that holds the registry path of the software key for the display adapter. Registry data should be written only to this path.


### -field TranslatedResourceList

A pointer to a <a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a> structure that holds the translated resources assigned to the display adapter.


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


The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function allocates a DXGK_DEVICE_INFO structure and calls <a href="..\dispmprt\nc-dispmprt-dxgkcb_get_device_information.md">DxgkCbGetDeviceInformation</a> to get that structure filled in with information about a display adapter. Five of the structure members (<b>Version</b>, <b>SystemMemorySize</b>, <b>HighestPhysicalAddress</b>, <b>AgpApertureBase</b>, and <b>AgpApertureSize</b>) hold general information and are not associated with a particular display adapter. Those members are included in the DXGK_DEVICE_INFO structure because they provide information that <i>DxgkDdiStartDevice</i> requires to initialize the driver and display adapter hardware.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>

<a href="..\dispmprt\nc-dispmprt-dxgkcb_get_device_information.md">DxgkCbGetDeviceInformation</a>

<a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_DEVICE_INFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

