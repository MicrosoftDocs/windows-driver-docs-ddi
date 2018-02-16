---
UID: NS:d3dkmddi._DXGKARG_ACQUIRESWIZZLINGRANGE
title: "_DXGKARG_ACQUIRESWIZZLINGRANGE"
author: windows-driver-content
description: The DXGKARG_ACQUIRESWIZZLINGRANGE structure describes parameters for making an allocation accessible through a CPU aperture.
old-location: display\dxgkarg_acquireswizzlingrange.htm
old-project: display
ms.assetid: 865f4d08-f2b3-4922-956f-2c49aa4e68b0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGKARG_ACQUIRESWIZZLINGRANGE, display.dxgkarg_acquireswizzlingrange, DmStructs_761fb707-877a-455c-b5cd-0c2e2b050aea.xml, *INOUT_PDXGKARG_ACQUIRESWIZZLINGRANGE, DXGKARG_ACQUIRESWIZZLINGRANGE, DXGKARG_ACQUIRESWIZZLINGRANGE structure [Display Devices], _DXGKARG_ACQUIRESWIZZLINGRANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	d3dkmddi.h
apiname:
-	DXGKARG_ACQUIRESWIZZLINGRANGE
product: Windows
targetos: Windows
req.typenames: DXGKARG_ACQUIRESWIZZLINGRANGE
---

# _DXGKARG_ACQUIRESWIZZLINGRANGE structure


## -description


The DXGKARG_ACQUIRESWIZZLINGRANGE structure describes parameters for making an allocation accessible through a CPU aperture.


## -syntax


````
typedef struct _DXGKARG_ACQUIRESWIZZLINGRANGE {
  HANDLE           hAllocation;
  UINT             PrivateDriverData;
  UINT             RangeId;
  UINT             SegmentId;
  SIZE_T           RangeSize;
  PHYSICAL_ADDRESS CPUTranslatedAddress;
} DXGKARG_ACQUIRESWIZZLINGRANGE;
````


## -struct-fields




### -field hAllocation

[in] A handle to the allocation that the display miniport driver assigned and that is returned through its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function.


### -field PrivateDriverData

[in] A UINT value of private data that the user-mode display driver sends when it calls the Microsoft Direct3D runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function. The private data should be an index that lets the display miniport driver determine the accessible part of the allocation (for example, the MIP level). This member should not contain a pointer.


### -field RangeId

[in] The zero-based identifier of the swizzling range that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a> function programs.


### -field SegmentId

[in] The identifier of a segment in which the allocation is currently paged.


### -field RangeSize

[in] The size, in bytes, of the range to acquire. This range size is identical to the size of the allocation that <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a> acquires a range for. The driver can modify the value in <b>RangeSize</b> when the <b>UseAlternateVA</b> bit-field flag is specified in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_lockflags.md">D3DDDICB_LOCKFLAGS</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function. If the <b>UseAlternateVA</b> flag is not specified, the driver cannot change <b>RangeSize</b>.


### -field CPUTranslatedAddress

[in/out] The base physical address where the CPU should map the allocation. The display miniport driver must set this information when a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a> function succeeds. 


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_lockflags.md">D3DDDICB_LOCKFLAGS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_ACQUIRESWIZZLINGRANGE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

