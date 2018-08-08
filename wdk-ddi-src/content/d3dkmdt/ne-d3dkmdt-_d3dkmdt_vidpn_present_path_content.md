---
UID: NE:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_CONTENT
title: "_D3DKMDT_VIDPN_PRESENT_PATH_CONTENT"
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_CONTENT enumeration is used to indicate the type of content that is displayed on a VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_content.htm
tech.root: display
ms.assetid: 29423933-c3cf-4fe4-b79c-f82718163a23
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH_CONTENT, D3DKMDT_VIDPN_PRESENT_PATH_CONTENT enumeration [Display Devices], D3DKMDT_VPPC_GRAPHICS, D3DKMDT_VPPC_NOTSPECIFIED, D3DKMDT_VPPC_UNINITIALIZED, D3DKMDT_VPPC_VIDEO, DmEnums_000ba351-38c5-4ab5-981c-15e4f44b3765.xml, _D3DKMDT_VIDPN_PRESENT_PATH_CONTENT, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_CONTENT, d3dkmdt/D3DKMDT_VPPC_GRAPHICS, d3dkmdt/D3DKMDT_VPPC_NOTSPECIFIED, d3dkmdt/D3DKMDT_VPPC_UNINITIALIZED, d3dkmdt/D3DKMDT_VPPC_VIDEO, display.d3dkmdt_vidpn_present_path_content
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_VIDPN_PRESENT_PATH_CONTENT
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_CONTENT
---

# _D3DKMDT_VIDPN_PRESENT_PATH_CONTENT enumeration


## -description


The D3DKMDT_VIDPN_PRESENT_PATH_CONTENT enumeration is used to indicate the type of content that is displayed on a VidPN present path.


## -enum-fields




### -field D3DKMDT_VPPC_UNINITIALIZED

Indicates that a variable of type D3DKMDT_VIDPN_PRESENT_PATH_CONTENT has not yet been assigned a meaningful value.


### -field D3DKMDT_VPPC_GRAPHICS

Indicates that the path displays graphics content.


### -field D3DKMDT_VPPC_VIDEO

Indicates that the path displays video content.


### -field D3DKMDT_VPPC_NOTSPECIFIED

Indicates that no content type has been specified.


## -remarks



The <b>Content</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a value from the D3DKMDT_VIDPN_PRESENT_PATH_CONTENT enumeration.



