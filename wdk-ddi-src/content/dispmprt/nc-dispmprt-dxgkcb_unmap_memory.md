---
UID: NC:dispmprt.DXGKCB_UNMAP_MEMORY
title: DXGKCB_UNMAP_MEMORY
author: windows-driver-content
description: The DxgkCbUnmapMemory function unmaps a range of addresses previously mapped by DxgkCbMapMemory.
old-location: display\dxgkcbunmapmemory.htm
old-project: display
ms.assetid: 71e8eb0e-599b-44cf-955b-828f6667edf6
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgkcbunmapmemory, DxgkCbUnmapMemory callback function [Display Devices], DxgkCbUnmapMemory, DXGKCB_UNMAP_MEMORY, DXGKCB_UNMAP_MEMORY, dispmprt/DxgkCbUnmapMemory, DpFunctions_d0ba5b02-22ab-4fad-a54a-1e402f538456.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
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
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkCbUnmapMemory
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKCB_UNMAP_MEMORY callback


## -description


The <b>DxgkCbUnmapMemory</b> function unmaps a range of addresses previously mapped by <a href="..\dispmprt\nc-dispmprt-dxgkcb_map_memory.md">DxgkCbMapMemory</a>.


## -prototype


````
DXGKCB_UNMAP_MEMORY DxgkCbUnmapMemory;

NTSTATUS DxgkCbUnmapMemory(
  _In_ HANDLE DeviceHandle,
  _In_ PVOID  VirtualAddress
)
{ ... }
````


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.


### -param VirtualAddress [in]

The beginning address of the range to be unmapped. This address can be a virtual address in system space, a virtual address in the address space of a user-mode process, or an address in I/O space.


## -returns



<b>DxgkCbUnmapMemory</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkcb_map_memory.md">DxgkCbMapMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_UNMAP_MEMORY callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

