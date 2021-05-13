---
UID: NE:d3dkmddi._DXGK_QUERYADAPTERINFOTYPE
title: DXGK_QUERYADAPTERINFOTYPE (d3dkmddi.h)
description: The DXGK_QUERYADAPTERINFOTYPE enumeration indicates the type of information to retrieve when a display miniport driver's DxgkDdiQueryAdapterInfo function is called.
old-location: display\dxgk_queryadapterinfotype.htm
ms.date: 05/13/2021
keywords: ["DXGK_QUERYADAPTERINFOTYPE enumeration"]
ms.keywords: DXGKQAITYPE_ALLOCATIONGROUP, DXGKQAITYPE_DISPLAY_DRIVERCAPS_EXTENSION, DXGKQAITYPE_DRIVERCAPS, DXGKQAITYPE_GPUMMUCAPS, DXGKQAITYPE_HISTORYBUFFERPRECISION, DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR, DXGKQAITYPE_NUMPOWERCOMPONENTS, DXGKQAITYPE_PAGETABLELEVELDESC, DXGKQAITYPE_PHYSICALADAPTERCAPS, DXGKQAITYPE_POWERCOMPONENTINFO, DXGKQAITYPE_POWERCOMPONENTPSTATEINFO, DXGKQAITYPE_PREFERREDGPUNODE, DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES, DXGKQAITYPE_QUERYSEGMENT, DXGKQAITYPE_QUERYSEGMENT2, DXGKQAITYPE_QUERYSEGMENT3, DXGKQAITYPE_QUERYSEGMENT4, DXGKQAITYPE_SEGMENTMEMORYSTATE, DXGKQAITYPE_UEFIFRAMEBUFFERRANGES, DXGKQAITYPE_UMDRIVERPRIVATE, DXGK_QUERYADAPTERINFOTYPE, DXGK_QUERYADAPTERINFOTYPE enumeration [Display Devices], DmEnums_c4637ac2-b8e0-4c30-a709-5a8ff1ee3fdc.xml, _DXGK_QUERYADAPTERINFOTYPE, d3dkmddi/DXGKQAITYPE_ALLOCATIONGROUP, d3dkmddi/DXGKQAITYPE_DISPLAY_DRIVERCAPS_EXTENSION, d3dkmddi/DXGKQAITYPE_DRIVERCAPS, d3dkmddi/DXGKQAITYPE_GPUMMUCAPS, d3dkmddi/DXGKQAITYPE_HISTORYBUFFERPRECISION, d3dkmddi/DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR, d3dkmddi/DXGKQAITYPE_NUMPOWERCOMPONENTS, d3dkmddi/DXGKQAITYPE_PAGETABLELEVELDESC, d3dkmddi/DXGKQAITYPE_PHYSICALADAPTERCAPS, d3dkmddi/DXGKQAITYPE_POWERCOMPONENTINFO, d3dkmddi/DXGKQAITYPE_POWERCOMPONENTPSTATEINFO, d3dkmddi/DXGKQAITYPE_PREFERREDGPUNODE, d3dkmddi/DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT2, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT3, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT4, d3dkmddi/DXGKQAITYPE_SEGMENTMEMORYSTATE, d3dkmddi/DXGKQAITYPE_UEFIFRAMEBUFFERRANGES, d3dkmddi/DXGKQAITYPE_UMDRIVERPRIVATE, d3dkmddi/DXGK_QUERYADAPTERINFOTYPE, display.dxgk_queryadapterinfotype
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
targetos: Windows
tech.root: display
req.typenames: DXGK_QUERYADAPTERINFOTYPE
ms.custom: 19H1
f1_keywords:
 - _DXGK_QUERYADAPTERINFOTYPE
 - d3dkmddi/_DXGK_QUERYADAPTERINFOTYPE
 - DXGK_QUERYADAPTERINFOTYPE
 - d3dkmddi/DXGK_QUERYADAPTERINFOTYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_QUERYADAPTERINFOTYPE
 - DXGK_QUERYADAPTERINFOTYPE
dev_langs:
 - c++
---

# DXGK_QUERYADAPTERINFOTYPE enumeration

## -description

The **DXGK_QUERYADAPTERINFOTYPE** enumeration indicates the type of information to retrieve when a display miniport driver's [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function is called.

## -enum-fields

### -field DXGKQAITYPE_UMDRIVERPRIVATE

Indicates a private, proprietary-defined data structure for the display driver.

### -field DXGKQAITYPE_DRIVERCAPS

The display miniport driver should populate a [**DXGK_DRIVERCAPS**](ns-d3dkmddi-_dxgk_drivercaps.md) structure with its driver capabilities.

### -field DXGKQAITYPE_QUERYSEGMENT

The display miniport driver should populate a [**DXGK_QUERYSEGMENTOUT**](ns-d3dkmddi-_dxgk_querysegmentout.md) structure with its memory-segment information.

### -field DXGKQAITYPE_RESERVED

Reserved for system use. Do not use in your driver. This constant occurs starting in Windows 7.

### -field DXGKQAITYPE_QUERYSEGMENT2

Reserved for system use. Do not use in your driver. This constant occurs starting in Windows 7.

### -field DXGKQAITYPE_QUERYSEGMENT3

The display miniport driver should populate a [**DXGK_QUERYSEGMENTOUT3**](ns-d3dkmddi-_dxgk_querysegmentout3.md) structure with memory-segment information. Supported starting in Windows 8.

### -field DXGKQAITYPE_NUMPOWERCOMPONENTS

The display miniport should provide a UINT value that specifies the number of power components that it uses. Supported starting in Windows 8.

### -field DXGKQAITYPE_POWERCOMPONENTINFO

The display miniport driver should populate a [**DXGK_POWER_RUNTIME_COMPONENT**](ns-d3dkmddi-_dxgk_power_runtime_component.md) structure with information about the *n*th power component, where *n* is the component index specified by **[DXGKARG_QUERYADAPTERINFO](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md).pInputData** in a call to [DxgkDdiQueryAdapterInfo](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md). Supported starting in Windows 8.

### -field DXGKQAITYPE_PREFERREDGPUNODE

Reserved for system use. Do not use in your driver. This constant occurs starting in Windows 8.

### -field DXGKQAITYPE_POWERCOMPONENTPSTATEINFO

Reserved for system use. Do not use in your driver. Supported starting in Windows 8.1.

### -field DXGKQAITYPE_HISTORYBUFFERPRECISION

The display miniport driver should populate a [**DXGKARG_HISTORYBUFFERPRECISION**](ns-d3dkmddi-_dxgkarg_historybufferprecision.md) structure with information about the precision of history buffer data that it uses. Supported starting in Windows 8.1.

### -field DXGKQAITYPE_QUERYSEGMENT4

The display miniport driver should populate a [**DXGK_QUERYSEGMENTOUT4**](ns-d3dkmddi-_dxgk_querysegmentout4.md) structure to indicate its memory-segment information. Supported starting in Windows 10.

### -field DXGKQAITYPE_SEGMENTMEMORYSTATE

The display miniport driver should populate a [**DXGK_MEMORYRANGE**](ns-d3dkmddi-_dxgk_memoryrange.md) structure with its bad memory ranges. Supported starting in Windows 10.

### -field DXGKQAITYPE_GPUMMUCAPS

The display miniport driver should populate a [**DXGK_GPUMMUCAPS**](ns-d3dkmddi-_dxgk_gpummucaps.md) structure with its virtual memory management capabilities. Supported starting in Windows 10.

### -field DXGKQAITYPE_PAGETABLELEVELDESC

Reserved for system use. Do not use in your driver. This constant occurs starting in Windows 10.

### -field DXGKQAITYPE_PHYSICALADAPTERCAPS

Reserved for system use. Do not use in your driver. This constant occurs starting in Windows 10.

### -field DXGKQAITYPE_DISPLAY_DRIVERCAPS_EXTENSION

Reserved for system use. Do not use in your driver. This constant occurs starting in Windows 10.

### -field DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR

Supported starting in Windows 10, version 1703. Indicates a request for an integrated panel descriptor where the input buffer to the query will be a [**DXGK_QUERYINTEGRATEDDISPLAYIN**](ns-d3dkmddi-_dxgk_qaitargetin.md) structure and the output buffer is a [**DXGK_QUERYINTEGRATEDDISPLAYOUT**](ns-d3dkmddi-_dxgk_queryintegrateddisplayout2.md) structure.

Although this function addresses a target, only DxgKrnl adapter locks are taken over this call, not child device locks. In practice, since this call will be made before the child device is exposed, there should be no concurrent DDI calls which address the same target.

NOTE: Unlike most QueryAdapterInfo calls, the output buffer size is variable although it is still known in advance from the DescriptorLength field of the [**DXGK_INTEGRATED_DISPLAY_CHILD**](../dispmprt/ns-dispmprt-_dxgk_integrated_display_child.md) structure for the target id. The size of the output buffer is:
```DescriptorLength + FIELD_OFFSET( DXGK_QUERYINTEGRATEDDISPLAYOUT, Descriptor )```.

### -field DXGKQAITYPE_UEFIFRAMEBUFFERRANGES

Indicates request for the UEFI frame buffer ranges. Supported starting in Windows 10, version 1703.

### -field DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES

Supported starting in Windows 10, version 1703. Indicates a request for colorimetry overrides for an external display, where the input buffer to the query will be a [**DXGK_QUERYCOLORIMETRYOVERRIDESIN**](ns-d3dkmddi-_dxgk_qaitargetin.md) structure, containing only the target id being addressed and the output buffer is a [**DXGK_COLORIMETRY**](ns-d3dkmddi-_dxgk_colorimetry.md) structure into which the driver writes overrides for the monitor attached to the target.

Although this function addresses a target, only DxgKrnl adapter locks are taken over this call, not child device locks.  Since this call will be made before the child device is exposed, there should be no concurrent DDI calls which address the same target.

The output buffer is zeroed when passed to the driver.  If the driver has no overrides for the monitor, it should return STATUS_SUCCESS and leave the output buffer zeroed.  If the driver has overrides, it fill in all fields of the DXGK_COLORIMETRY to describe the monitor capabilities as the OS will not accept partial overrides.

### -field DXGKQAITYPE_DISPLAYID_DESCRIPTOR

Indicates a request for an integrated panel descriptor where the input buffer to the query will be a [**DXGK_QAITARGETIN**](ns-d3dkmddi-_dxgk_qaitargetin.md) structure and the output buffer is a [**DXGK_QUERYINTEGRATEDDISPLAYOUT**](ns-d3dkmddi-_dxgk_queryintegrateddisplayout2.md) structure. Supported starting in Windows 10, version 1709.

### -field DXGKQAITYPE_FRAMEBUFFERSAVESIZE

The display miniport driver should populate a [**DXGK_FRAMEBUFFERSAVEAREA**](ns-d3dkmddi-_dxgk_framebuffersavearea.md) structure with the size of the frame buffer to save to system memory during power transitions. Supported starting in Windows 10, version 1803.

### -field DXGKQAITYPE_HARDWARERESERVEDRANGES

The display miniport driver should populate a [**DXGK_HARDWARERESERVEDRANGES**](ns-d3dkmddi-_dxgk_hardwarereservedranges.md) structure with its hardware reserved memory ranges. Supported starting in Windows 10, version 1803.

### -field DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR2

Supported starting in Windows 10, version 1803. Indicates a request for an integrated panel descriptor where the input buffer to the query will be a [**DXGK_QAITARGETIN**](ns-d3dkmddi-_dxgk_qaitargetin.md) structure and the output buffer is a [**DXGK_QUERYINTEGRATEDDISPLAYOUT2**](ns-d3dkmddi-_dxgk_queryintegrateddisplayout2.md) structure. This query replaces use of the **DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR** query for WDDM 2.4 drivers.

[**TypeIntegratedDisplay** child devices](../dispmprt/ne-dispmprt-_dxgk_child_device_type.md) are reported by calling [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) with the *Type* set to this value.

### -field DXGKQAITYPE_NODEPERFDATA

A [**DXGK_NODE_PERFDATA**](../d3dkmdt/ns-d3dkmdt-_dxgk_node_perfdata.md) structure that represents performance data collected per engine from an adapter on an interval basis. Supported starting in Windows 10, version 1803.

### -field DXGKQAITYPE_ADAPTERPERFDATA

A [**DXGK_ADAPTER_PERFDATA**](../d3dkmdt/ns-d3dkmdt-_dxgk_adapter_perfdata.md) structure that represents performance data collected per adapter on an interval basis. Supported starting in Windows 10, version 1803.

### -field DXGKQAITYPE_ADAPTERPERFDATA_CAPS

A [**DXGK_ADAPTER_PERFDATACAPS**](../d3dkmdt/ns-d3dkmdt-_dxgk_adapter_perfdatacaps.md) structure that represents data capabilities that are static and queried once per GPU during initialization. Supported starting in Windows 10, version 1803.

### -field DXGKQAITYPE_GPUVERSION

A [**DXGK_GPUVERSION**](../d3dkmdt/ns-d3dkmdt-_dxgk_gpuversion.md) structure used to collect the BIOS version and GPU architecture name once during GPU initialization. Supported starting in Windows 10, version 1803.

### -field DXGKQAITYPE_DEVICE_TYPE_CAPS

A [**DXGK_DEVICE_TYPE_CAPS**](ns-d3dkmddi-_dxgk_device_type_caps.md) structure that describes the type of capabilities for a device. Supported starting in Windows 10, version 1809.

### -field DXGKQAITYPE_WDDMDEVICECAPS

A [**DXGK_WDDMDEVICECAPS**](ns-d3dkmddi-_dxgk_wddmdevicecaps.md) structure that contains the WDDM capabilities that are queried by the OS during device initialization. Supported starting in Windows 10, version 1903.

### -field DXGKQAITYPE_GPUPCAPS

A [**DXGK_GPUPCAPS**](ns-d3dkmddi-_dxgk_gpupcaps.md) structure that contains the GPU capabilities for a kernel mode display driver. Supported starting in Windows 10, version 1903.

### -field DXGKQAITYPE_QUERYTARGETGAMMACAPS

A [**DXGK_TARGET_GAMMA_CAPS**](ns-d3dkmddi-dxgk_target_gamma_caps.md) structure that describes the gamma capabilities of the display miniport driver. Supported starting in Windows 10, version 1903.

### -field DXGKQAITYPE_SCANOUT_CAPS

A DXGK_QUERY_SCANOUT_CAPS_OUT structure that describes the scanout capabilities of the driver. Supported starting in Windows 10, version 1903.

### -field DXGKQAITYPE_PHYSICAL_MEMORY_CAPS

A [**DXGKQAITYPE_PHYSICAL_MEMORY_CAPS**](ns-d3dkmddi-dxgk_physical_memory_caps.md) structure that describes the physical memory restrictions (the highest visible physical address) of the device. Supported starting in Windows Server 2022.

See **DXGKQAITYPE_IOMMU_CAPS** for details on how to indicate driver support for IOMMU linear remapping.

### -field DXGKQAITYPE_IOMMU_CAPS

A [**DXGK_IOMMU_CAPS**](ns-d3dkmddi-dxgk_iommu_caps.md) structure that indicates that IOMMU linear remapping is supported by the driver. Supported starting in Windows Server 2022. To indicate support for linear remapping, the driver must also inform *Dxgkernel* about its physical memory restrictions through the **DXGKQAITYPE_PHYSICAL_MEMORY_CAPS** cap.

Logical remapping can only be done if no existing physical memory is referenced by the device, so *Dxgkrnl*'s call sequence is as follows:

* Call [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) for all physical adapters, so that the driver can gather information for all linked physical adapters.

* Call [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) with DXGKQAITYPE_PHYSICAL_MEMORY_CAPS and DXGKQAITYPE_IOMMU_CAPS so that it can then create and attach the device to an IOMMU domain before any memory can be accessed.

* Call [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) to start the device.

## -remarks

*Dxgkrnl* calls the display miniport driver's [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) callback to retrieve configuration information from the graphics adapter. The driver fills the requested information in the buffer pointed to by the **pOutputData** member of the [**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md) structure. See each enumeration value for the type of structure to fill in.

## -see-also

[DXGKARG_QUERYADAPTERINFO](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md)

[DxgkDdiQueryAdapterInfo](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
