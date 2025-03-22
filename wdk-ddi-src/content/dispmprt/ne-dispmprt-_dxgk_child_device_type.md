---
UID: NE:dispmprt._DXGK_CHILD_DEVICE_TYPE
title: DXGK_CHILD_DEVICE_TYPE (dispmprt.h)
description: Learn more about the DXGK_CHILD_DEVICE_TYPE enumeration.
tech.root: display
ms.date: 05/20/2024
keywords: ["DXGK_CHILD_DEVICE_TYPE enumeration"]
ms.keywords: "*PDXGK_CHILD_DEVICE_TYPE, DXGK_CHILD_DEVICE_TYPE, DXGK_CHILD_DEVICE_TYPE enumeration [Display Devices], DmEnums_afd3654c-ffb4-49d6-ba59-235148e59d2c.xml, PDXGK_CHILD_DEVICE_TYPE, PDXGK_CHILD_DEVICE_TYPE enumeration pointer [Display Devices], TypeIntegratedDisplay, TypeOther, TypeUninitialized, TypeVideoOutput, _DXGK_CHILD_DEVICE_TYPE, display.dxgk_child_device_type, dispmprt/DXGK_CHILD_DEVICE_TYPE, dispmprt/PDXGK_CHILD_DEVICE_TYPE, dispmprt/TypeIntegratedDisplay, dispmprt/TypeOther, dispmprt/TypeUninitialized, dispmprt/TypeVideoOutput"
req.header: dispmprt.h
req.construct-type: enumeration
req.include-header: Dispmprt.h
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
req.irql: 
targetos: Windows
req.typenames: DXGK_CHILD_DEVICE_TYPE, *PDXGK_CHILD_DEVICE_TYPE
f1_keywords:
 - _DXGK_CHILD_DEVICE_TYPE
 - dispmprt/_DXGK_CHILD_DEVICE_TYPE
 - PDXGK_CHILD_DEVICE_TYPE
 - dispmprt/PDXGK_CHILD_DEVICE_TYPE
 - DXGK_CHILD_DEVICE_TYPE
 - dispmprt/DXGK_CHILD_DEVICE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_CHILD_DEVICE_TYPE
 - PDXGK_CHILD_DEVICE_TYPE
 - DXGK_CHILD_DEVICE_TYPE
---

# DXGK_CHILD_DEVICE_TYPE enumeration (dispmprt.h)



## -description

The **DXGK_CHILD_DEVICE_TYPE** enumeration indicates the type of a child device of the display adapter.

## -enum-fields

### -field TypeUninitialized

Indicates that a variable of type **DXGK_CHILD_DEVICE_TYPE** has not yet been assigned a meaningful value.

### -field TypeVideoOutput

Indicates that the child device is a video output. A video output is the circuitry on the display adapter that supplies a video signal to an external or integrated monitor (or other display device). Note that monitors, integrated LCD panels, and other devices that actually display an image are not considered child devices of the display adapter.

### -field TypeOther

Indicates that the child device is not a video output. TV tuners, crossbar switches, and MPEG2 codecs are examples of child devices that are not video outputs.

### -field TypeIntegratedDisplay

Type indicating that this target is permanently connected to an integrated display.

### -field TypeLogicalGpu

This value represents a logical GPU. In a system with multiple physical GPUs, a logical GPU could be a virtual representation of a single GPU or a combination of multiple GPUs working together as a single entity. (Examples include CrossFile and SLI technologies.)

## -remarks

The **ChildDeviceType** member of a [**DXGK_CHILD_DESCRIPTOR**](ns-dispmprt-_dxgk_child_descriptor.md) structure is a **DXGK_CHILD_DEVICE_TYPE** value.

For more information about child devices of display adapters, see [Child Devices of the Display Adapter](/windows-hardware/drivers/display/child-devices-of-the-display-adapter) and [Enumerating Child Devices of a Display Adapter](/windows-hardware/drivers/display/enumerating-child-devices-of-a-display-adapter).

## -see-also

[**DXGK_CHILD_DESCRIPTOR**](ns-dispmprt-_dxgk_child_descriptor.md)

[**DxgkDdiQueryChildRelations**](nc-dispmprt-dxgkddi_query_child_relations.md)
