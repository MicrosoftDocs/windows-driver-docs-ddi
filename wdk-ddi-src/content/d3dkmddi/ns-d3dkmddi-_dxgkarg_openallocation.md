---
UID: NS:d3dkmddi._DXGKARG_OPENALLOCATION
title: "_DXGKARG_OPENALLOCATION"
author: windows-driver-content
description: The DXGKARG_OPENALLOCATION structure describes allocations that the display miniport driver should open.
old-location: display\dxgkarg_openallocation.htm
old-project: display
ms.assetid: cddb85c7-137c-4ceb-b53c-170ce020cea1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: d3dkmddi/DXGKARG_OPENALLOCATION, DmStructs_442924a2-c130-487c-acdb-62a2b6e9f219.xml, display.dxgkarg_openallocation, _DXGKARG_OPENALLOCATION, DXGKARG_OPENALLOCATION structure [Display Devices], DXGKARG_OPENALLOCATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available beginning with Windows Vista.
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
-	d3dkmddi.h
apiname:
-	DXGKARG_OPENALLOCATION
product: Windows
targetos: Windows
req.typenames: DXGKARG_OPENALLOCATION
---

# _DXGKARG_OPENALLOCATION structure


## -description


The DXGKARG_OPENALLOCATION structure describes allocations that the display miniport driver should open.


## -syntax


````
typedef struct _DXGKARG_OPENALLOCATION {
  UINT                     NumAllocations;
  DXGK_OPENALLOCATIONINFO  *pOpenAllocation;
  VOID                     *pPrivateDriverData;
  UINT                     PrivateDriverSize;
  DXGK_OPENALLOCATIONFLAGS Flags;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  UINT                     SubresourceIndex;
  SIZE_T                   SubresourceOffset;
  UINT                     Pitch;
#endif 
} DXGKARG_OPENALLOCATION;
````


## -struct-fields




### -field NumAllocations

[in] The number of elements in the array that the <b>pOpenAllocation</b> member specifies, which represents the number of device-specific allocations to open.


### -field pOpenAllocation

[in/out] An array of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_openallocationinfo.md">DXGK_OPENALLOCATIONINFO</a> structures for the allocations to open.


### -field pPrivateDriverData

[in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver. This block of private data is the same resource-specific data that is passed in the <b>pPrivateDriverData</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a> structure in the call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function. The display miniport driver cannot modify this block of private data.


### -field PrivateDriverSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_openallocationflags.md">DXGK_OPENALLOCATIONFLAGS</a> structure that identifies the operation to perform for allocations.


### -field SubresourceIndex

[in] Supported beginning with Windows 8.

An index into the resource for the render target surface.

The operating system specifies this member only if the display miniport driver supports <a href="https://msdn.microsoft.com/03db58e6-a6d5-4b6f-ba71-d22a985f9c57">GDI Hardware Acceleration</a>. Specifically, the display miniport driver must implement  the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_renderkm.md">DxgkDdiRenderKm</a> function and must create the device with the <b>GdiDevice</b> member set in <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a>.<b>Flags</b>.

If the value of <b>SubresourceIndex</b> is greater than the number of subresources in the allocation, the display miniport driver should return an error.


### -field SubresourceOffset

[out] Supported beginning with Windows 8.

The offset, in bytes, from the start of the allocation to the start of the subresource.


### -field Pitch

[out] Supported beginning with Windows 8.

The pitch, in bytes, of the allocation—that is, the distance, in bytes, to the start of the next row.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_openallocationinfo.md">DXGK_OPENALLOCATIONINFO</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_openallocationflags.md">DXGK_OPENALLOCATIONFLAGS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_OPENALLOCATION structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

