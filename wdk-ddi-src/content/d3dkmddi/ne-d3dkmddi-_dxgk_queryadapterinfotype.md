---
UID: NE:d3dkmddi._DXGK_QUERYADAPTERINFOTYPE
title: _DXGK_QUERYADAPTERINFOTYPE (d3dkmddi.h)
description: The DXGK_QUERYADAPTERINFOTYPE enumeration indicates the type of information to retrieve.
old-location: display\dxgk_queryadapterinfotype.htm

ms.assetid: 5cceffb1-853c-4635-b855-d0e3f107c23d
ms.date: 04/16/2018
ms.keywords: DXGKQAITYPE_ALLOCATIONGROUP, DXGKQAITYPE_DISPLAY_DRIVERCAPS_EXTENSION, DXGKQAITYPE_DRIVERCAPS, DXGKQAITYPE_GPUMMUCAPS, DXGKQAITYPE_HISTORYBUFFERPRECISION, DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR, DXGKQAITYPE_NUMPOWERCOMPONENTS, DXGKQAITYPE_PAGETABLELEVELDESC, DXGKQAITYPE_PHYSICALADAPTERCAPS, DXGKQAITYPE_POWERCOMPONENTINFO, DXGKQAITYPE_POWERCOMPONENTPSTATEINFO, DXGKQAITYPE_PREFERREDGPUNODE, DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES, DXGKQAITYPE_QUERYSEGMENT, DXGKQAITYPE_QUERYSEGMENT2, DXGKQAITYPE_QUERYSEGMENT3, DXGKQAITYPE_QUERYSEGMENT4, DXGKQAITYPE_SEGMENTMEMORYSTATE, DXGKQAITYPE_UEFIFRAMEBUFFERRANGES, DXGKQAITYPE_UMDRIVERPRIVATE, DXGK_QUERYADAPTERINFOTYPE, DXGK_QUERYADAPTERINFOTYPE enumeration [Display Devices], DmEnums_c4637ac2-b8e0-4c30-a709-5a8ff1ee3fdc.xml, _DXGK_QUERYADAPTERINFOTYPE, d3dkmddi/DXGKQAITYPE_ALLOCATIONGROUP, d3dkmddi/DXGKQAITYPE_DISPLAY_DRIVERCAPS_EXTENSION, d3dkmddi/DXGKQAITYPE_DRIVERCAPS, d3dkmddi/DXGKQAITYPE_GPUMMUCAPS, d3dkmddi/DXGKQAITYPE_HISTORYBUFFERPRECISION, d3dkmddi/DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR, d3dkmddi/DXGKQAITYPE_NUMPOWERCOMPONENTS, d3dkmddi/DXGKQAITYPE_PAGETABLELEVELDESC, d3dkmddi/DXGKQAITYPE_PHYSICALADAPTERCAPS, d3dkmddi/DXGKQAITYPE_POWERCOMPONENTINFO, d3dkmddi/DXGKQAITYPE_POWERCOMPONENTPSTATEINFO, d3dkmddi/DXGKQAITYPE_PREFERREDGPUNODE, d3dkmddi/DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT2, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT3, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT4, d3dkmddi/DXGKQAITYPE_SEGMENTMEMORYSTATE, d3dkmddi/DXGKQAITYPE_UEFIFRAMEBUFFERRANGES, d3dkmddi/DXGKQAITYPE_UMDRIVERPRIVATE, d3dkmddi/DXGK_QUERYADAPTERINFOTYPE, display.dxgk_queryadapterinfotype
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
topic_type:
- APIRef
- kbSyntax
api_type:
-	 HeaderDef
api_location:
-	 d3dkmddi.h
api_name:
-	 DXGK_QUERYADAPTERINFOTYPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_QUERYADAPTERINFOTYPE
---

# _DXGK_QUERYADAPTERINFOTYPE enumeration


## -description


The DXGK_QUERYADAPTERINFOTYPE enumeration indicates the type of information to retrieve.


## -syntax


```cpp
typedef enum _DXGK_QUERYADAPTERINFOTYPE {
  DXGKQAITYPE_UMDRIVERPRIVATE                   = 0,
  DXGKQAITYPE_DRIVERCAPS                        = 1,
  DXGKQAITYPE_QUERYSEGMENT                      = 2,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7)
  DXGKQAITYPE_ALLOCATIONGROUP                   = 3,
  DXGKQAITYPE_QUERYSEGMENT2                     = 4,
#endif
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  DXGKQAITYPE_QUERYSEGMENT3                     = 5,
  DXGKQAITYPE_NUMPOWERCOMPONENTS                = 6,
  DXGKQAITYPE_POWERCOMPONENTINFO                = 7,
  DXGKQAITYPE_PREFERREDGPUNODE                  = 8,
#endif
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  DXGKQAITYPE_POWERCOMPONENTPSTATEINFO          = 9,
  DXGKQAITYPE_HISTORYBUFFERPRECISION            = 10,
#endif
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
  DXGKQAITYPE_QUERYSEGMENT4                     = 11,
  DXGKQAITYPE_SEGMENTMEMORYSTATE                = 12,
  DXGKQAITYPE_GPUMMUCAPS                        = 13,
  DXGKQAITYPE_PAGETABLELEVELDESC                = 14,
  DXGKQAITYPE_PHYSICALADAPTERCAPS               = 15,
  DXGKQAITYPE_DISPLAY_DRIVERCAPS_EXTENSION      = 16,
#endif
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_2)
  DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR     = 17,
  DXGKQAITYPE_UEFIFRAMEBUFFERRANGES             = 18,
  DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES         = 19
} DXGK_QUERYADAPTERINFOTYPE;
```


## -enum-fields




### -field DXGKQAITYPE_UMDRIVERPRIVATE

Indicates private data for the user-mode display driver.


### -field DXGKQAITYPE_DRIVERCAPS

Indicates the driver capabilities in a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure.


### -field DXGKQAITYPE_QUERYSEGMENT


Indicates memory-segment information in a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout.md">DXGK_QUERYSEGMENTOUT</a> structure.

### -field DXGKQAITYPE_RESERVED

Reserved for system use. Do not use in your driver. Note that this constant occurs starting with Windows 7.

### -field DXGKQAITYPE_QUERYSEGMENT2

Reserved for system use. Do not use in your driver.

Note that this constant occurs starting with Windows 7.


### -field DXGKQAITYPE_QUERYSEGMENT3

Indicates memory-segment information in a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout3.md">DXGK_QUERYSEGMENTOUT3</a> structure.

Supported starting with Windows 8.


### -field DXGKQAITYPE_NUMPOWERCOMPONENTS

Indicates the number of power components used by the display miniport driver.  For more information, see Remarks.

Supported starting with Windows 8.


### -field DXGKQAITYPE_POWERCOMPONENTINFO

Indicates information about power components used by the display miniport driver. For more information, see Remarks.

Supported starting with Windows 8.


### -field DXGKQAITYPE_PREFERREDGPUNODE

Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.


### -field DXGKQAITYPE_POWERCOMPONENTPSTATEINFO

Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.1.


### -field DXGKQAITYPE_HISTORYBUFFERPRECISION

Indicates info about the precision of history buffer data used by the display miniport driver. For more information, see Remarks.

Supported starting with Windows 8.1.


### -field DXGKQAITYPE_QUERYSEGMENT4

Indicates memory-segment information in a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout4.md">DXGK_QUERYSEGMENTOUT4</a> structure.

Supported starting with Windows 10.


### -field DXGKQAITYPE_SEGMENTMEMORYSTATE

Indicates bad memory ranges in a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_memoryrange.md">DXGK_MEMORYRANGE</a> structure.

Supported starting with Windows 10.


### -field DXGKQAITYPE_GPUMMUCAPS

Indicates physical adapter GPU capabilities.

Supported starting with Windows 10.


### -field DXGKQAITYPE_PAGETABLELEVELDESC

Reserved for system use. Do not use in your driver.


### -field DXGKQAITYPE_PHYSICALADAPTERCAPS

Reserved for system use. Do not use in your driver.


### -field DXGKQAITYPE_DISPLAY_DRIVERCAPS_EXTENSION

Reserved for system use. Do not use in your driver.


### -field DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR

Indicates a request for an integrated panel descriptor where the input buffer to the query will be a DXGK_QUERYINTEGRATEDDISPLAYIN structure and the output buffer is a DXGK_QUERYINTEGRATEDDISPLAYOUT structure.

Although this function addresses a target, only DxgKrnl adapter locks are taken over this call, not child device locks.  In practice, since this call will be made before the child device is exposed, there should be no concurrent DDI calls which address the same target.

<div class="alert"><b>Note</b>  Unlike most QueryAdapterInfo calls, the output buffer size is variable although it is still known in advance from the DescriptorLength field of the DXGK_INTEGRATED_DISPLAY_CHILD structure for the target id.  The size of the output buffer is:
DescriptorLength + FIELD_OFFSET( DXGK_QUERYINTEGRATEDDISPLAYOUT, Descriptor )
</div>
<div> </div>

### -field DXGKQAITYPE_UEFIFRAMEBUFFERRANGES

Indicates request for the UEFI frame buffer ranges.


### -field DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES

Indicates a request for colorimetry overrides for an external display where the input buffer to the query will be a DXGK_QUERYCOLORIMETRYOVERRIDESIN structure, containing only the target id being addressed and the output buffer is a DXGK_COLORIMETRY structure into which the driver writes overrides for the monitor attached to the target.

Although this function addresses a target, only DxgKrnl adapter locks are taken over this call, not child device locks.  Since this call will be made before the child device is exposed, there should be no concurrent DDI calls which address the same target.

The output buffer is zeroed when passed to the driver.  If the driver has no overrides for the monitor, it should return STATUS_SUCCESS and leave the output buffer zeroed.  If the driver has overrides, it fill in all fields of the DXGK_COLORIMETRY to describe the monitor capabilities as the OS will not accept partial overrides.


### -field DXGKQAITYPE_DISPLAYID_DESCRIPTOR

Indicates a request for an integrated panel descriptor where the input buffer to the query will be a DXGK_QAITARGETIN structure and the output buffer is a DXGK_QUERYINTEGRATEDDISPLAYOUT structure.

### -field DXGKQAITYPE_FRAMEBUFFERSAVESIZE

The size of the frame buffer to save to system memory during power transitions.

### -field DXGKQAITYPE_HARDWARERESERVEDRANGES

Reserved ranges.

### -field DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR2

Indicates a request for an integrated panel descriptor where the input buffer to the query will be a DXGK_QAITARGETIN structure and the output buffer is a [DXGK_QUERYINTEGRATEDDISPLAYOUT2](ns-d3dkmddi-_dxgk_queryintegrateddisplayout2.md) structure. This query replaces use of the DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR query for WDDM 2.4 drivers.

TypeIntegratedDisplay child devices are reported by calling [DXGKDDI_QUERYADAPTERINFO](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) with the *Type* set to this value.

### -field DXGKQAITYPE_NODEPERFDATA

Represents performance data collected per engine from an adapter on an interval basis.

### -field DXGKQAITYPE_ADAPTERPERFDATA

Represents performance data collected per adapter on an interval basis.

### -field DXGKQAITYPE_ADAPTERPERFDATA_CAPS

Represents data caps that are static and queried once per GPU during initialization.

### -field DXGKQAITYPE_GPUVERSION

Used to collect the bios version and GPU architecture name once during GPU initialization.


### -field DXGKQAITYPE_DEVICE_TYPE_CAPS

The device type capabilities.

### -field DXGKQAITYPE_WDDMDEVICECAPS

The device capabilities that are queried by the OS during device initialization.

### -field DXGKQAITYPE_GPUPCAPS

## -remarks



The display miniport driver must fill the buffer pointed to by the <b>pOutputData</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a> structure as follows:

| **Value of [DXGKARG_QUERYADAPTERINFO](vscode-resource://c:/drivers/wdk-ddi/wdk-ddi-src/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo.md) .Type** | **Contents of output buffer pointed to by [DXGKARG_QUERYADAPTERINFO](vscode-resource://c:/drivers/wdk-ddi/wdk-ddi-src/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo.md) .pOutputData** | 
|:--|:--|
| **DXGKQAITYPE_UMDRIVERPRIVATE** | Proprietary buffer | 
| **DXGKQAITYPE_DRIVERCAPS** | Populated [DXGK_DRIVERCAPS](vscode-resource://c:/drivers/wdk-ddi/wdk-ddi-src/content/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps.md)  structure | 
| **DXGKQAITYPE_QUERYSEGMENT** | Populated [DXGK_QUERYSEGMENTOUT](vscode-resource://c:/drivers/wdk-ddi/wdk-ddi-src/content/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentout.md)  structure | 
| **DXGKQAITYPE_QUERYSEGMENT3** | Populated [DXGK_QUERYSEGMENTOUT3](vscode-resource://c:/drivers/wdk-ddi/wdk-ddi-src/content/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentout3.md) structure | 
| **DXGKQAITYPE_NUMPOWERCOMPONENTS** | A UINT value that specifies the number of power components used by the display miniport driver | 
| **DXGKQAITYPE_POWERCOMPONENTINFO** | Populated [DXGK_POWER_RUNTIME_COMPONENT](vscode-resource://c:/drivers/wdk-ddi/wdk-ddi-src/content/d3dkmddi/ns-d3dkmddi-_dxgk_power_runtime_component.md)  structure that provides information about the nth power component, where n is the component index specified by [DXGKARG_QUERYADAPTERINFO](vscode-resource://c:/drivers/wdk-ddi/wdk-ddi-src/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo.md) .pInputData in a call to the [DxgkDdiQueryAdapterInfo](vscode-resource://c:/drivers/wdk-ddi/wdk-ddi-src/content/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo.md)  function | 
| **DXGKQAITYPE_HISTORYBUFFERPRECISION** | Populated [DXGKARG_HISTORYBUFFERPRECISION](vscode-resource://c:/drivers/wdk-ddi/wdk-ddi-src/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_historybufferprecision.md) structure |

## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout3.md">DXGK_QUERYSEGMENTOUT3</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout.md">DXGK_QUERYSEGMENTOUT</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_historybufferprecision.md">DXGKARG_HISTORYBUFFERPRECISION</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_power_runtime_component.md">DXGK_POWER_RUNTIME_COMPONENT</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>



 

 


