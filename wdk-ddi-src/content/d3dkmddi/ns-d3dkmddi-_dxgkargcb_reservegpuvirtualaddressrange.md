---
UID: NS:d3dkmddi._DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
title: "_DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE"
author: windows-driver-content
description: DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE is used with the DxgkCbReserveGpuVirtualAddressRangedevice driver interface (DDI) to allow the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process.
old-location: display\dxgkargcb_reservegpuvirtualaddressrange.htm
old-project: display
ms.assetid: D555E595-4319-4FCC-84A7-52FA3F278FFD
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE, _DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE, *INOUT_PDXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE, DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE structure [Display Devices], display.dxgkargcb_reservegpuvirtualaddressrange, d3dkmddi/DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dkmddi.h
apiname:
-	DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
product: Windows
targetos: Windows
req.typenames: DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
---

# _DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE structure


## -description


<b>DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE</b> is used with the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange.md">DxgkCbReserveGpuVirtualAddressRange</a>device driver interface (DDI) to allow the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process. 


## -syntax


````
typedef struct _DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE {
  HANDLE hDxgkProcess;
  UINT64 SizeInBytes;
  UINT   Alignment;
  UINT64 StartVirtualAddress;
  UINT64 BaseAddress;
  union {
    struct {
      UINT AllowUserModeMapping  :1;
    };
    UINT   Flags;
  };
} DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE;
````


## -struct-fields




### -field hDxgkProcess

The handle that was passed to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a>.


### -field SizeInBytes

The size of the address range in bytes, this must be set to an integral multiple of the address space covered by a single page table entry.


### -field Alignment

The number of bytes to align the start address to. Must be a multiple of the address space covered by a single page table entry and a power of 2.


### -field StartVirtualAddress

The starting location of the reserved address range.


### -field BaseAddress

The base virtual address of the virtual address range in bytes. It must be aligned to the size of the address space, covered by a single page table entry.


### -field AllowUserModeMapping

Allow the user mode driver to map allocations to the range.


### -field Flags

A single value containing the flags set in the structure.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange.md">DxgkCbReserveGpuVirtualAddressRange</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

