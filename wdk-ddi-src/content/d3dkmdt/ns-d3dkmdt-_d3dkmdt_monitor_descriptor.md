---
UID: NS:d3dkmdt._D3DKMDT_MONITOR_DESCRIPTOR
title: _D3DKMDT_MONITOR_DESCRIPTOR (d3dkmdt.h)
description: The D3DKMDT_MONITOR_DESCRIPTOR structure contains a pointer to a monitor descriptor along with information about the monitor descriptor.
old-location: display\d3dkmdt_monitor_descriptor.htm
tech.root: display
ms.assetid: 4bdce35f-adce-4898-8ef5-011a5476065a
ms.date: 05/10/2018
keywords: ["D3DKMDT_MONITOR_DESCRIPTOR structure"]
ms.keywords: D3DKMDT_MONITOR_DESCRIPTOR, D3DKMDT_MONITOR_DESCRIPTOR structure [Display Devices], DmStructs_760a75c4-4db4-445e-a63b-7e77b6b69090.xml, _D3DKMDT_MONITOR_DESCRIPTOR, d3dkmdt/D3DKMDT_MONITOR_DESCRIPTOR, display.d3dkmdt_monitor_descriptor
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.typenames: D3DKMDT_MONITOR_DESCRIPTOR
f1_keywords:
 - _D3DKMDT_MONITOR_DESCRIPTOR
 - d3dkmdt/_D3DKMDT_MONITOR_DESCRIPTOR
 - D3DKMDT_MONITOR_DESCRIPTOR
 - d3dkmdt/D3DKMDT_MONITOR_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - D3DKMDT_MONITOR_DESCRIPTOR
---

# _D3DKMDT_MONITOR_DESCRIPTOR structure


## -description

The D3DKMDT_MONITOR_DESCRIPTOR structure contains a pointer to a monitor descriptor along with information about the monitor descriptor.

## -struct-fields

### -field Id

An integer that identifies the monitor descriptor.

### -field Type

A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_monitor_descriptor_type">D3DKMDT_MONITOR_DESCRIPTOR_TYPE</a> enumeration that indicates the descriptor type.

### -field DataSize

The size, in bytes, of the monitor descriptor.

### -field pData

A pointer to the monitor descriptor.

### -field Origin

A value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_monitor_capabilities_origin">D3DKMDT_MONITOR_CAPABILITIES_ORIGIN</a> that indicates the source of the mode information for the monitor. For example, the mode information could be from a default monitor profile or it could be from an override in an INF file.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_monitor_capabilities_origin">D3DKMDT_MONITOR_CAPABILITIES_ORIGIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_monitor_descriptor_type">D3DKMDT_MONITOR_DESCRIPTOR_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Monitor Descriptor Set Interface</a>

