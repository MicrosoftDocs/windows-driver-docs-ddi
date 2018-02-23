---
UID: NS:dispmprt._DXGK_START_INFO
title: "_DXGK_START_INFO"
author: windows-driver-content
description: The DXGK_START_INFO structure holds information that is needed by the display miniport driver's DxgkDdiStartDevice function.
old-location: display\dxgk_start_info.htm
old-project: display
ms.assetid: 4d28bc79-5145-48a0-99e8-3f81b2ec4a05
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "_DXGK_START_INFO, dispmprt/PDXGK_START_INFO, dispmprt/DXGK_START_INFO, PDXGK_START_INFO structure pointer [Display Devices], display.dxgk_start_info, PDXGK_START_INFO, *PDXGK_START_INFO, DmStructs_c2f6faad-cd05-43ea-ab58-b296bc130e09.xml, DXGK_START_INFO, DXGK_START_INFO structure [Display Devices]"
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
-	DXGK_START_INFO
product: Windows
targetos: Windows
req.typenames: DXGK_START_INFO, *PDXGK_START_INFO
---

# _DXGK_START_INFO structure


## -description


The DXGK_START_INFO structure holds information that is needed by the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


## -syntax


````
typedef struct _DXGK_START_INFO {
  ULONG RequiredDmaQueueEntry;
  GUID  AdapterGuid;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  LUID  AdapterLuid;
#endif 
} DXGK_START_INFO, *PDXGK_START_INFO;
````


## -struct-fields




### -field RequiredDmaQueueEntry

The number of DMA buffers that the display miniport driver (or the display adapter) must be able to hold in a queue. The display miniport driver must preallocate all resources required to accommodate this number of DMA buffers. 


### -field AdapterGuid

A GUID that will serve as an identifier for the adapter being started.


### -field AdapterLuid

Available starting with Windows 8.

A locally unique identifier (LUID) that will serve as an identifier for the adapter being started.


## -remarks



The DirectX graphics kernel subsystem submits DMA buffers to the display miniport driver by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a>.

The <i>DxgkStartInfo</i> parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function is a pointer to a DXGK_START_INFO structure. 



