---
UID: NE:d3dkmdt._DXGK_CHILD_DEVICE_HPD_AWARENESS
title: _DXGK_CHILD_DEVICE_HPD_AWARENESS (d3dkmdt.h)
description: The DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration is used to describe the hot plug capabilities of a child device of a display adapter.
old-location: display\dxgk_child_device_hpd_awareness.htm
tech.root: display
ms.assetid: daef347a-26d4-46cf-82b4-a5852fe49b71
ms.date: 05/10/2018
ms.keywords: "*PDXGK_CHILD_DEVICE_HPD_AWARENESS, DXGK_CHILD_DEVICE_HPD_AWARENESS, DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration [Display Devices], DmEnums_1d5801e8-cb03-4409-a037-b25242176eea.xml, HpdAwarenessAlwaysConnected, HpdAwarenessInterruptible, HpdAwarenessNone, HpdAwarenessPolled, HpdAwarenessUninitialized, PDXGK_CHILD_DEVICE_HPD_AWARENESS, PDXGK_CHILD_DEVICE_HPD_AWARENESS enumeration pointer [Display Devices], _DXGK_CHILD_DEVICE_HPD_AWARENESS, d3dkmdt/DXGK_CHILD_DEVICE_HPD_AWARENESS, d3dkmdt/HpdAwarenessAlwaysConnected, d3dkmdt/HpdAwarenessInterruptible, d3dkmdt/HpdAwarenessNone, d3dkmdt/HpdAwarenessPolled, d3dkmdt/HpdAwarenessUninitialized, d3dkmdt/PDXGK_CHILD_DEVICE_HPD_AWARENESS, display.dxgk_child_device_hpd_awareness"
ms.topic: enum
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- DXGK_CHILD_DEVICE_HPD_AWARENESS
product:
- Windows
targetos: Windows
req.typenames: DXGK_CHILD_DEVICE_HPD_AWARENESS, *PDXGK_CHILD_DEVICE_HPD_AWARENESS
---

# _DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration


## -description


The DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration is used to describe the hot plug capabilities of a child device of a display adapter.


## -enum-fields




### -field HpdAwarenessUninitialized

Indicates that a variable of type DXGK_CHILD_DEVICE_HPD_AWARENESS has not yet been assigned a meaningful value.


### -field HpdAwarenessAlwaysConnected

Indicates that the child device is always connected; that is, it does not serve as a connector for external devices.


### -field HpdAwarenessNone

Reserved for system use. You should not use this value.


### -field HpdAwarenessPolled

Indicates that the display miniport driver is able to determine whether an external device is connected to the child device by polling the child device.


### -field HpdAwarenessInterruptible

Indicates that the child device is able to generate an interrupt when an external device is connected or disconnected.


## -remarks



The <b>ChildCapabilities</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structure is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_child_capabilities">DXGK_CHILD_CAPABILITIES</a> structure. The <b>HpdAwareness</b> member of a <b>DXGK_CHILD_DEVICE_HPD_AWARENESS</b> structure is a <b>DXGK_CHILD_CAPABILITIES</b>  structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>
 

 

