---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT
title: "_D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT"
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT structure is used to indicate the angles of rotation that are supported by a particular VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_rotation_support.htm
old-project: display
ms.assetid: f60cd2cf-23b6-4fed-8548-d0483fb17fe1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT, D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT structure [Display Devices], DmStructs_a078867c-e6a4-4bbf-afb6-244b210a5671.xml, _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT, display.d3dkmdt_vidpn_present_path_rotation_support
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT
---

# _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT structure


## -description


The <b>D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT</b> structure is used to indicate the angles of rotation that are supported by a particular VidPN present path.


## -struct-fields




### -field Identity

The path is capable of displaying content with no rotation.


### -field Rotate90

The path is capable of displaying content that is rotated 90 degrees.


### -field Rotate180

The path is capable of displaying content that is rotated 180 degrees.


### -field Rotate270

The path is capable of displaying content that is rotated 270 degrees.


### -field Offset0

The path adds no rotational offset. For more info, see <a href="https://msdn.microsoft.com/0c9bdd42-aeaf-4cc8-a979-9ed8eeda3811">Clone-mode requirements starting with Windows 8.1 Update</a>.

Supported starting with Windows 8.1 Update.


### -field Offset90

The path adds a rotational offset of 90 degrees. For more info, see <a href="https://msdn.microsoft.com/0c9bdd42-aeaf-4cc8-a979-9ed8eeda3811">Clone-mode requirements starting with Windows 8.1 Update</a>.

Supported starting with Windows 8.1 Update.


### -field Offset180

The path adds a rotational offset of 180 degrees. For more info, see <a href="https://msdn.microsoft.com/0c9bdd42-aeaf-4cc8-a979-9ed8eeda3811">Clone-mode requirements starting with Windows 8.1 Update</a>.

Supported starting with Windows 8.1 Update.


### -field Offset270

The path adds a rotational offset of 270 degrees. For more info, see <a href="https://msdn.microsoft.com/0c9bdd42-aeaf-4cc8-a979-9ed8eeda3811">Clone-mode requirements starting with Windows 8.1 Update</a>.

Supported starting with Windows 8.1 Update.


## -remarks



The <b>RotationSupport</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546719">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> structure is a <b>D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT</b> structure.

<div class="alert"><b>Note</b>  The operating system  does not update the value of the interface version value <b>DXGKDDI_INTERFACE_VERSION</b> to <b>DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION</b>. If you want to use the path-independent members in this structure, you should be sure that the interface version in your driver is &gt;= <b>DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION</b> (0x4003).</div>
<div> </div>


