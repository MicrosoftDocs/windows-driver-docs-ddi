---
UID: NS:d3dkmthk._D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN
title: "_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN"
author: windows-driver-content
description: The D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN structure identifies a flip present-history operation.
old-location: display\d3dkmt_flipmodel_presenthistorytoken.htm
old-project: display
ms.assetid: dcf844e3-3346-485e-8965-c8cb824e2c78
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN, D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN, d3dkmthk/D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN, display.d3dkmt_flipmodel_presenthistorytoken, D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN structure [Display Devices], OpenGL_Structs_819c22ef-0bae-476a-9cbc-0169cd7fc82f.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN
product: Windows
targetos: Windows
req.typenames: D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN
---

# _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN structure


## -description


The D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN structure identifies a flip present-history operation.


## -syntax


````
typedef struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN {
  UINT64                                    FenceValue;
  ULONG64                                   hLogicalSurface;
  UINT                                      SwapChainIndex;
  UINT64                                    PresentLimitSemaphoreId;
  D3DDDI_FLIPINTERVAL_TYPE                  FlipInterval;
  D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS Flags;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  LONG64                                    hCompSurf;
  UINT64                                    CompositionSyncKey;
  UINT                                      RemainingTokens;
  RECT                                      ScrollRect;
  POINT                                     ScrollOffset;
  UINT                                      PresentCount;
  FLOAT                                     RevealColor[4];
  D3DDDI_ROTATION                           Rotation;
  D3DKMT_SCATTERBLTS                        ScatterBlts;
  D3DKMT_HANDLE                             hSyncObject;
#endif 
  D3DKMT_DIRTYREGIONS                       DirtyRegions;
} D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN;
````


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

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs).


### -field Flags

[in] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_flipmodel_presenthistorytokenflags.md">D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS</a> structure that identifies, in bit-field flags, attributes of a flip present-history operation.


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

[in] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_dirtyregions.md">D3DKMT_DIRTYREGIONS</a> structure that identifies the active rectangles (dirty regions) of the flip surface.


#### - ScatterBlts

This member is reserved and should be set to zero.

Supported starting with Windows 8.


#### - hSyncObject

This member is reserved and should be set to zero.

Supported starting with Windows 8.


## -see-also

<a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_dirtyregions.md">D3DKMT_DIRTYREGIONS</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presenthistorytoken.md">D3DKMT_PRESENTHISTORYTOKEN</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_flipmodel_presenthistorytokenflags.md">D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

