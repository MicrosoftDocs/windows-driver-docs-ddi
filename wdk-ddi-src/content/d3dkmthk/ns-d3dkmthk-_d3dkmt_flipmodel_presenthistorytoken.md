---
UID: NS:d3dkmthk._D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN
title: "_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN"
author: windows-driver-content
description: The D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN structure identifies a flip present-history operation.
old-location: display\d3dkmt_flipmodel_presenthistorytoken.htm
old-project: display
ms.assetid: dcf844e3-3346-485e-8965-c8cb824e2c78
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN, D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN structure [Display Devices], OpenGL_Structs_819c22ef-0bae-476a-9cbc-0169cd7fc82f.xml, _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN, d3dkmthk/D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN, display.d3dkmt_flipmodel_presenthistorytoken
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN is Supported starting with the Windows 7 operating system.
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
-	d3dkmthk.h
api_name:
-	D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN
product: Windows
targetos: Windows
req.typenames: D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN
---

# _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN structure


## -description


The D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN structure identifies a flip present-history operation.


## -struct-fields




### -field FenceValue

[in] A 64-bit value that specifies the fence value that is used for the flip.


### -field hLogicalSurface

[in] A 64-bit value that specifies the handle to a logical surface.


### -field dxgContext

 


### -field VidPnSourceId

 


### -field SwapChainIndex

[in] The index of the surface in the swap chain that is used for the flip.


### -field PresentLimitSemaphoreId

[in] A 64-bit value that identifies the present-limit semaphore.


### -field FlipInterval

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544549">D3DDDI_FLIPINTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs).


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff547991">D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS</a> structure that identifies, in bit-field flags, attributes of a flip present-history operation.


### -field hCompSurf

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field compSurfLuid

 


### -field confirmationCookie

 


### -field CompositionSyncKey

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field RemainingTokens

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field ScrollRect

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field ScrollOffset

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field PresentCount

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field RevealColor

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field Rotation

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field Reserved

 


### -field SourceRect

 


### -field DestWidth

 


### -field DestHeight

 


### -field TargetRect

 


### -field Transform

 


### -field CustomDuration

 


### -field CustomDurationFlipInterval

 


### -field PlaneIndex

 


### -field ColorSpace

 


### -field DirtyRegions

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff547937">D3DKMT_DIRTYREGIONS</a> structure that identifies the active rectangles (dirty regions) of the flip surface.


#### - ScatterBlts

This member is reserved and should be set to zero.

Supported starting with Windows 8.


#### - hSyncObject

This member is reserved and should be set to zero.

Supported starting with Windows 8.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544549">D3DDDI_FLIPINTERVAL_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547937">D3DKMT_DIRTYREGIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547991">D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548188">D3DKMT_PRESENTHISTORYTOKEN</a>
 

 

