---
UID: NS:d3dkmddi._DXGK_PAGETABLEUPDATEADDRESS
title: _DXGK_PAGETABLEUPDATEADDRESS
author: windows-driver-content
description: DXGK_PAGETABLEUPDATEADDRESS contains the address of a page table to update. The member containing the address is defined as part of a DxgkDdiBuildPagingBuffer operation in the DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE structure.
old-location: display\dxgk_pagetableupdateaddress.htm
old-project: display
ms.assetid: 39013276-C76A-4E31-80DD-26C17A020BD6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PAGETABLEUPDATEADDRESS, display.dxgk_pagetableupdateaddress, DXGK_PAGETABLEUPDATEADDRESS structure [Display Devices], DXGK_PAGETABLEUPDATEADDRESS, d3dkmddi/DXGK_PAGETABLEUPDATEADDRESS
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
-	DXGK_PAGETABLEUPDATEADDRESS
product: Windows
targetos: Windows
req.typenames: DXGK_PAGETABLEUPDATEADDRESS
---

# _DXGK_PAGETABLEUPDATEADDRESS structure


## -description


<b>DXGK_PAGETABLEUPDATEADDRESS</b> contains the address of a page table to update. The member containing the address is defined as part of a <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> operation in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_updatepagetable.md">DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE</a> structure.


## -syntax


````
typedef struct _DXGK_PAGETABLEUPDATEADDRESS {
  union {
    PVOID                   CpuVirtual;
    D3DGPU_PHYSICAL_ADDRESS GpuPhysical;
    D3DGPU_VIRTUAL_ADDRESS  GpuVirtual;
  };
} DXGK_PAGETABLEUPDATEADDRESS;
````


## -struct-fields




### -field CpuVirtual

The CPU virtual address of the page table to update.


### -field GpuPhysical

The GPU physical address of the page table to update.


### -field GpuVirtual

The GPU virtual address of the page table to update.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_updatepagetable.md">DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_PAGETABLEUPDATEADDRESS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

