---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT
title: _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT (d3dkmdt.h)
description: The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure is used to indicate the types of copy protection that are supported by a particular VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_copyprotection_support.htm
tech.root: display
ms.assetid: 2b0c7428-bc88-461c-ab72-daccf02606da
ms.date: 05/10/2018
keywords: ["D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure"]
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT, D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure [Display Devices], DmStructs_01eb8f42-1ba1-46e3-9b56-99952e5fedbe.xml, _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT, display.d3dkmdt_vidpn_present_path_copyprotection_support
f1_keywords:
 - "d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT"
 - "D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT
---

# _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure


## -description


The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure is used to indicate the types of copy protection that are supported by a particular VidPN present path.


## -struct-fields




### -field NoProtection

The path is not capable of providing any copy protection.


### -field MacroVisionApsTrigger

The path is capable of providing Rovi (formerly Macrovision) analog protection support (APS). 


### -field MacroVisionFull

The path is capable of providing full Rovi (formerly Macrovision) copy protection.


### -field Reserved

Reserved for future use.


## -remarks



The <b>CopyProtectionSupport</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_copyprotection">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION</a> structure is a D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure.



