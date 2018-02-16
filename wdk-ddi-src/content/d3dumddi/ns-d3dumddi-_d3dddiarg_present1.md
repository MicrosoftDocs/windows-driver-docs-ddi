---
UID: NS:d3dumddi._D3DDDIARG_PRESENT1
title: "_D3DDDIARG_PRESENT1"
author: windows-driver-content
description: Describes a resource to display. Used with the pfnPresent1(D3D) function by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\d3dddiarg_present1.htm
old-project: display
ms.assetid: 17EBEEF1-4C86-4948-AADA-669B2952755A
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/D3DDDIARG_PRESENT1, _D3DDDIARG_PRESENT1, display.d3dddiarg_present1, D3DDDIARG_PRESENT1, D3DDDIARG_PRESENT1 structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: TBD
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_PRESENT1
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_PRESENT1
---

# _D3DDDIARG_PRESENT1 structure


## -description


Describes a resource to display. Used with the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present1.md">pfnPresent1(D3D)</a> function by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -syntax


````
typedef struct D3DDDIARG_PRESENT1 {
  D3DDDIARG_PRESENTSURFACE *phSrcResources;
  UINT                     SrcResources;
  HANDLE                   hDstResource;
  UINT                     DstSubResourceIndex;
  D3DDDI_PRESENTFLAGS      Flags;
  D3DDDI_FLIPINTERVAL_TYPE FlipInterval;
  UINT                     Reserved;
  const RECT               *pDirtyRects;
  UINT                     DirtyRects;
} D3DDDIARG_PRESENT1;
````


## -struct-fields




### -field phSrcResources

[in] An array of non-<b>NULL</b> handles and zero-based indices to the source resource to display or to release. <b>phSrcResources</b> is always a valid handle for a resource to display.


### -field SrcResources

[in] The number of source resources that are in the array pointed to by <b>phSrcResources.</b>


### -field hDstResource

[in] A handle to the destination resource to display to. If <b>NULL</b>, the destination is unknown, and the display miniport driver determines the destination just before the hardware command stream is processed.


### -field DstSubResourceIndex


      [in] The zero-based index into the destination resource, which is specified by the handle in the <b>hDstResource</b> member. This index indicates the subresource or surface to display to.


### -field Flags

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_presentflags.md">D3DDDI_PRESENTFLAGS</a> structure that identifies, in bit-field flags, how to display. 


### -field FlipInterval

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). 


### -field Reserved

This member is reserved and should be set to zero.


### -field pDirtyRects

[in] A pointer to an array of dirty rectangles (<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>s), relative to the source rectangle <b>SrcRect</b>, that indicate the portion of the overlay plane that has changed.

The driver can use this member to perform optimizations, though it's not required to use the dirty rectangle info. However, the driver should never fail a function call based on the provided dirty rectangles.


### -field DirtyRects

[in] The number of dirty rectangles in the array pointed to by <b>pDirtyRects</b>.


### -field BackBufferMultiplicity

 




## -see-also

<a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_presentflags.md">D3DDDI_PRESENTFLAGS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present1.md">pfnPresent1(D3D)</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_presentcb.md">pfnPresentCb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_PRESENT1 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

