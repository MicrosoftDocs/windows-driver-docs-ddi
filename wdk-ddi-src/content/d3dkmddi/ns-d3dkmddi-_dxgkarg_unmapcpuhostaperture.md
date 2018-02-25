---
UID: NS:d3dkmddi._DXGKARG_UNMAPCPUHOSTAPERTURE
title: "_DXGKARG_UNMAPCPUHOSTAPERTURE"
author: windows-driver-content
description: The DXGKARG_UNMAPCPUHOSTAPERTURE structure is used to unmap a previously mapped range of the CPU host aperture.
old-location: display\dxgkarg_unmapcpuhostaperture.htm
old-project: display
ms.assetid: 22482590-B0F7-4F35-95D5-9B352810047D
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, C, D, DXGKARG_UNMAPCPUHOSTAPERTURE, DXGKARG_UNMAPCPUHOSTAPERTURE structure [Display Devices], E, G, H, K, M, N, O, P, R, S, T, U, X, _, _DXGKARG_UNMAPCPUHOSTAPERTURE, d3dkmddi/DXGKARG_UNMAPCPUHOSTAPERTURE, display.dxgkarg_unmapcpuhostaperture"
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
-	DXGKARG_UNMAPCPUHOSTAPERTURE
product: Windows
targetos: Windows
req.typenames: DXGKARG_UNMAPCPUHOSTAPERTURE
---

# _DXGKARG_UNMAPCPUHOSTAPERTURE structure


## -description


The <b>DXGKARG_UNMAPCPUHOSTAPERTURE</b> structure is used to unmap a previously mapped range of the CPU host aperture.


## -syntax


````
typedef struct _DXGKARG_UNMAPCPUHOSTAPERTURE {
  UINT64  NumberOfPages;
  UINT32* pCpuHostAperturePages;
  WORD    SegmentId;
  WORD    PhysicalAdapterIndex;
} DXGKARG_UNMAPCPUHOSTAPERTURE;
````


## -struct-fields




### -field NumberOfPages

Specifies the number of pages being unmapped.


### -field pCpuHostAperturePages

Array of CPU host aperture pages to unmap. This is an array of page indices from the start of the CPU host aperture physical address.


### -field SegmentId

The driver segment identifier (starting from 1) of the segment for which the CPU host aperture is unmapped.


### -field PhysicalAdapterIndex

The zero-based physical adapter index in a linked display adapter link.

<div class="alert"><b>Note</b>  The page size is equal to the segment page size.</div>
<div> </div>

## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_unmapcpuhostaperture.md">DxgkDdiUnmapCpuHostAperture</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_UNMAPCPUHOSTAPERTURE structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

