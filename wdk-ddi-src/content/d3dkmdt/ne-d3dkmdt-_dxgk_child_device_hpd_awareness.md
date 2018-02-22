---
UID: NE:d3dkmdt._DXGK_CHILD_DEVICE_HPD_AWARENESS
title: "_DXGK_CHILD_DEVICE_HPD_AWARENESS"
author: windows-driver-content
description: The DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration is used to describe the hot plug capabilities of a child device of a display adapter.
old-location: display\dxgk_child_device_hpd_awareness.htm
old-project: display
ms.assetid: daef347a-26d4-46cf-82b4-a5852fe49b71
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: HpdAwarenessPolled, *PDXGK_CHILD_DEVICE_HPD_AWARENESS, PDXGK_CHILD_DEVICE_HPD_AWARENESS, DXGK_CHILD_DEVICE_HPD_AWARENESS, DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration [Display Devices], d3dkmdt/HpdAwarenessAlwaysConnected, d3dkmdt/PDXGK_CHILD_DEVICE_HPD_AWARENESS, d3dkmdt/HpdAwarenessNone, HpdAwarenessAlwaysConnected, d3dkmdt/HpdAwarenessPolled, HpdAwarenessInterruptible, d3dkmdt/HpdAwarenessInterruptible, HpdAwarenessNone, _DXGK_CHILD_DEVICE_HPD_AWARENESS, d3dkmdt/HpdAwarenessUninitialized, PDXGK_CHILD_DEVICE_HPD_AWARENESS enumeration pointer [Display Devices], d3dkmdt/DXGK_CHILD_DEVICE_HPD_AWARENESS, HpdAwarenessUninitialized, DmEnums_1d5801e8-cb03-4409-a037-b25242176eea.xml, display.dxgk_child_device_hpd_awareness
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	DXGK_CHILD_DEVICE_HPD_AWARENESS
product: Windows
targetos: Windows
req.typenames: "*PDXGK_CHILD_DEVICE_HPD_AWARENESS, DXGK_CHILD_DEVICE_HPD_AWARENESS"
---

# _DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration


## -description


The DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration is used to describe the hot plug capabilities of a child device of a display adapter.


## -syntax


````
typedef enum _DXGK_CHILD_DEVICE_HPD_AWARENESS { 
  HpdAwarenessUninitialized    = 0,
  HpdAwarenessAlwaysConnected  = 1,
  HpdAwarenessNone             = 2,
  HpdAwarenessPolled           = 3,
  HpdAwarenessInterruptible    = 4
} DXGK_CHILD_DEVICE_HPD_AWARENESS, *PDXGK_CHILD_DEVICE_HPD_AWARENESS;
````


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



The <b>ChildCapabilities</b> member of a <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structure is a <a href="..\dispmprt\ns-dispmprt-_dxgk_child_capabilities.md">DXGK_CHILD_CAPABILITIES</a> structure. The <b>HpdAwareness</b> member of a <b>DXGK_CHILD_DEVICE_HPD_AWARENESS</b> structure is a <b>DXGK_CHILD_CAPABILITIES</b>  structure.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

