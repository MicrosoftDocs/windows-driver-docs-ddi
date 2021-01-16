---
UID: NS:dispmprt._DXGK_DEVICE_DESCRIPTOR
title: _DXGK_DEVICE_DESCRIPTOR (dispmprt.h)
description: The DXGK_DEVICE_DESCRIPTOR structure is used by the display port driver to request that the display miniport driver return all or a portion of a monitor's Extended Display Identification Data (EDID).
old-location: display\dxgk_device_descriptor.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGK_DEVICE_DESCRIPTOR structure"]
ms.keywords: "*PDXGK_DEVICE_DESCRIPTOR, DXGK_DEVICE_DESCRIPTOR, DXGK_DEVICE_DESCRIPTOR structure [Display Devices], DmStructs_d66c7175-e264-49f4-94ce-f4a92a678010.xml, PDXGK_DEVICE_DESCRIPTOR, PDXGK_DEVICE_DESCRIPTOR structure pointer [Display Devices], _DXGK_DEVICE_DESCRIPTOR, display.dxgk_device_descriptor, dispmprt/DXGK_DEVICE_DESCRIPTOR, dispmprt/PDXGK_DEVICE_DESCRIPTOR"
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
req.typenames: DXGK_DEVICE_DESCRIPTOR, *PDXGK_DEVICE_DESCRIPTOR
f1_keywords:
 - _DXGK_DEVICE_DESCRIPTOR
 - dispmprt/_DXGK_DEVICE_DESCRIPTOR
 - PDXGK_DEVICE_DESCRIPTOR
 - dispmprt/PDXGK_DEVICE_DESCRIPTOR
 - DXGK_DEVICE_DESCRIPTOR
 - dispmprt/DXGK_DEVICE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DEVICE_DESCRIPTOR
 - PDXGK_DEVICE_DESCRIPTOR
 - DXGK_DEVICE_DESCRIPTOR
---

# _DXGK_DEVICE_DESCRIPTOR structure


## -description

The DXGK_DEVICE_DESCRIPTOR structure is used by the display port driver to request that the display miniport driver return all or a portion of a monitor's Extended Display Identification Data (EDID).

## -struct-fields

### -field DescriptorOffset

An integer that indicates an offset, in bytes, into the EDID. This member specifies the beginning of the requested data.

### -field DescriptorLength

An integer that indicates the length, in bytes, of the buffer pointed to by <b>DescriptorBuffer</b>.

### -field DescriptorBuffer

A pointer to a buffer that receives all or a portion of the monitor's EDID. This buffer is allocated by the display port driver and filled in by the display miniport driver. The display miniport driver must not write more than <b>DescriptorLength</b> bytes to this buffer.

## -remarks

The display port driver passes a DXGK_DEVICE_DESCRIPTOR structure to <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_device_descriptor">DxgkDdiQueryDeviceDescriptor</a> to request that the display miniport driver return all or a portion of a monitor's EDID. The desired portion of the EDID is specified by the <b>DescriptorOffset</b> and <b>DescriptorLength</b> members. For example, to request 256 bytes, starting at an offset of 128 bytes into a monitor's EDID, the display port driver would set <b>DescriptorOffset</b> to 128, and <b>DescriptorLength</b> to 256.

## -see-also

<a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_generic_descriptor">DXGK_GENERIC_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_device_descriptor">DxgkDdiQueryDeviceDescriptor</a>

