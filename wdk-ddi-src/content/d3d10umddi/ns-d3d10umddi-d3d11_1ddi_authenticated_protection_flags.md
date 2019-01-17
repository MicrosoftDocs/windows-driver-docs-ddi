---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS
title: D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS
description: Specifies the protection level for video content.
old-location: display\d3d11_1ddi_authenticated_protection_flags.htm
ms.assetid: 687eb573-ea7c-4e8a-80df-65339521ec18
ms.date: 05/10/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS, D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS, display.d3d11_1ddi_authenticated_protection_flags
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS
---

# D3D11_1DDI_AUTHENTICATED_PROTECTION_FLAGS structure


## -description


Specifies the protection level for video content.


## -struct-fields




### -field ProtectionEnabled

If 1, video content protection is enabled.


### -field OverlayOrFullscreenRequired

If 1, the application requires video to be displayed using either a hardware overlay or full-screen exclusive mode.




### -field Reserved

Reserved for system use. Set all bits to zero.


### -field Value

Use this member to access all of the bits in the union.

