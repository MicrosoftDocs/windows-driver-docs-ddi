---
UID: NS:d3dkmddi._DXGKARG_FLIPOVERLAY
title: _DXGKARG_FLIPOVERLAY
author: windows-driver-content
description: The DXGKARG_FLIPOVERLAY structure describes a new allocation to display for the overlay.
old-location: display\dxgkarg_flipoverlay.htm
old-project: display
ms.assetid: c5396581-e9f2-47eb-bb82-1e54f5def4d0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKARG_FLIPOVERLAY, DXGKARG_FLIPOVERLAY, DmStructs_8ff06344-e7f5-44b1-95fc-d3b363428d43.xml, display.dxgkarg_flipoverlay, DXGKARG_FLIPOVERLAY structure [Display Devices], d3dkmddi/DXGKARG_FLIPOVERLAY
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
-	DXGKARG_FLIPOVERLAY
product: Windows
targetos: Windows
req.typenames: DXGKARG_FLIPOVERLAY
---

# _DXGKARG_FLIPOVERLAY structure


## -description


The DXGKARG_FLIPOVERLAY structure describes a new allocation to display for the overlay. 


## -syntax


````
typedef struct _DXGKARG_FLIPOVERLAY {
  HANDLE           hSource;
  PHYSICAL_ADDRESS SrcPhysicalAddress;
  UINT             SrcSegmentId;
  VOID             *pPrivateDriverData;
  UINT             PrivateDriverDataSize;
} DXGKARG_FLIPOVERLAY;
````


## -struct-fields




### -field hSource

[in] A handle to the source allocation to be displayed.


### -field SrcPhysicalAddress

[in] The physical address, within the segment that <b>SrcSegmentId</b> specifies, of the allocation to be displayed.


### -field SrcSegmentId

[in] The identifier of a segment in which the allocation is currently paged.


### -field pPrivateDriverData

[in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_flipoverlay.md">DxgkDdiFlipOverlay</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_FLIPOVERLAY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

