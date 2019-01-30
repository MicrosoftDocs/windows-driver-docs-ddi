---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT
title: "_D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT" (d3dkmdt.h)
description: The D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT structure is used to indicate the types of scaling (and centering) that are supported by a particular VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_scaling_support.htm
tech.root: display
ms.assetid: 44b7f841-40e5-4d7d-adca-b70b4a8ef55c
ms.date: 05/10/2018
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT, D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT structure [Display Devices], DmStructs_8a17e0fc-7c6c-4c95-bbdb-471beef9e830.xml, _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT, display.d3dkmdt_vidpn_present_path_scaling_support
ms.topic: struct
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
-	D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT
---

# _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT structure


## -description


The D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT structure is used to indicate the types of scaling (and centering) that are supported by a particular VidPN present path.


## -struct-fields




### -field Identity

The path is capable of displaying content with no transformation.


### -field Centered

The path is capable of displaying centered content.


### -field Stretched

The path is capable of displaying scaled content.


### -field AspectRatioCenteredMax

The path is capable of scaling source content to fit the target while preserving the aspect ratio of the source.

This member is available beginning with Windows 7.


### -field Custom

The path is capable of displaying one or more scaling modes that are not described by other members of this structure.


## -remarks



The <b>ScalingSupport</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546719">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> structure is a D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546706">D3DKMDT_VIDPN_PRESENT_PATH_SCALING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546719">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a>
 

 

