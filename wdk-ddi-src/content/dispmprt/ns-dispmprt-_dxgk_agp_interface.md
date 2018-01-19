---
UID: NS:dispmprt._DXGK_AGP_INTERFACE
title: _DXGK_AGP_INTERFACE
author: windows-driver-content
description: The DXGK_AGP_INTERFACE structure contains pointers to functions in the AGP interface, which is implemented by the display port driver.
old-location: display\dxgk_agp_interface.htm
old-project: display
ms.assetid: ebaa2aba-426f-4f5f-b2bf-a8433cdc9205
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_AGP_INTERFACE, DXGK_AGP_INTERFACE, *PDXGK_AGP_INTERFACE
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
req.alt-api: DXGK_AGP_INTERFACE
req.alt-loc: dispmprt.h
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
req.typenames: DXGK_AGP_INTERFACE, *PDXGK_AGP_INTERFACE
---

# _DXGK_AGP_INTERFACE structure



## -description
The DXGK_AGP_INTERFACE structure contains pointers to functions in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538228">AGP interface</a>, which is implemented by the display port driver.



## -syntax

````
typedef struct _DXGK_AGP_INTERFACE {
  USHORT                   Size;
  USHORT                   Version;
  PVOID                    Context;
  PINTERFACE_REFERENCE     InterfaceReference;
  PINTERFACE_DEREFERENCE   InterfaceDereference;
  DXGKCB_AGP_ALLOCATE_POOL AgpAllocatePool;
  DXGKCB_AGP_FREE_POOL     AgpFreePool;
  DXGKCB_AGP_SET_COMMAND   AgpSetCommand;
} DXGK_AGP_INTERFACE, *PDXGK_AGP_INTERFACE;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field Version

The version number of the AGP interface. Version number constants are defined in <i>Dispmprt.h</i> (for example, DXGK_AGP_INTERFACE_VERSION_1).


### -field Context

A pointer to a context that is provided by the display port driver.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display port driver.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display port driver.


### -field AgpAllocatePool

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_agp_allocate_pool.md">AgpAllocatePool</a> function.


### -field AgpFreePool

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_agp_free_pool.md">AgpFreePool</a> function.


### -field AgpSetCommand

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_agp_set_command.md">AgpSetCommand</a> function.


## -remarks
The display miniport driver supplies the <b>Size</b> and <b>Version</b> members of this structure, and then calls <a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a>, which fills in the remaining members of this structure.</p>