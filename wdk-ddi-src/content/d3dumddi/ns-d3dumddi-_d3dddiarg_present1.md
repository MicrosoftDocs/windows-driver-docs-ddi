---
UID: NS:d3dumddi._D3DDDIARG_PRESENT1
title: "_D3DDDIARG_PRESENT1"
author: windows-driver-content
description: Describes a resource to display. Used with the pfnPresent1(D3D) function by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\d3dddiarg_present1.htm
tech.root: display
ms.assetid: 17EBEEF1-4C86-4948-AADA-669B2952755A
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDIARG_PRESENT1, D3DDDIARG_PRESENT1 structure [Display Devices], _D3DDDIARG_PRESENT1, d3dumddi/D3DDDIARG_PRESENT1, display.d3dddiarg_present1
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_PRESENT1
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_PRESENT1
---

# _D3DDDIARG_PRESENT1 structure


## -description


Describes a resource to display. Used with the <a href="https://msdn.microsoft.com/8BB8E85F-B081-422E-ACE1-C2312BA28B9F">pfnPresent1(D3D)</a> function by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


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

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544639">D3DDDI_PRESENTFLAGS</a> structure that identifies, in bit-field flags, how to display. 


### -field FlipInterval

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544549">D3DDDI_FLIPINTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). 


### -field Reserved

This member is reserved and should be set to zero.


### -field pDirtyRects

[in] A pointer to an array of dirty rectangles (<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>s), relative to the source rectangle <b>SrcRect</b>, that indicate the portion of the overlay plane that has changed.

The driver can use this member to perform optimizations, though it's not required to use the dirty rectangle info. However, the driver should never fail a function call based on the provided dirty rectangles.


### -field DirtyRects

[in] The number of dirty rectangles in the array pointed to by <b>pDirtyRects</b>.


### -field BackBufferMultiplicity

 
The number of physical back buffer per logical back buffer.



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544549">D3DDDI_FLIPINTERVAL_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544639">D3DDDI_PRESENTFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



<a href="https://msdn.microsoft.com/8BB8E85F-B081-422E-ACE1-C2312BA28B9F">pfnPresent1(D3D)</a>



<a href="https://msdn.microsoft.com/460b9be5-5817-4225-9089-f86ad64f4554">pfnPresentCb</a>
 

 

