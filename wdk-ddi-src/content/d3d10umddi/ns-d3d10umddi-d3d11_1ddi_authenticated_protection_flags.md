---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS
title: D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS
author: windows-driver-content
description: Specifies the protection level for video content.
old-location: display\d3d11_1ddi_authenticated_protection_flags.htm
old-project: display
ms.assetid: 687eb573-ea7c-4e8a-80df-65339521ec18
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 1, 3, A, C, D, D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS, D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS structure [Display Devices], E, F, G, H, I, L, N, O, P, R, S, T, U, _, d3d10umddi/D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS, display.d3d11_1ddi_authenticated_protection_flags"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS
---

# D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS structure


## -description


Specifies the protection level for video content.


## -syntax


````
typedef struct D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS {
  union {
    struct {
      UINT ProtectionEnabled  :1;
      UINT OverlayOrFullscreenRequired  :1;
      UINT Reserved  :30;
    };
    UINT   Value;
  };
} D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS;
````


## -struct-fields




### -field ProtectionEnabled

If 1, video content protection is enabled.


### -field OverlayOrFullscreenRequired

If 1, the application requires video to be displayed using either a hardware overlay or full-screen exclusive mode.




### -field Reserved

Reserved for system use. Set all bits to zero.


#### - Value

Use this member to access all of the bits in the union.

