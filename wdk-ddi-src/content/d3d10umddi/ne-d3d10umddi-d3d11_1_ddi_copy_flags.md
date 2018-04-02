---
UID: NE:d3d10umddi.D3D11_1_DDI_COPY_FLAGS
title: D3D11_1_DDI_COPY_FLAGS
author: windows-driver-content
description: Specifies how to handle the existing contents of a resource during a copy or update operation of a region within that resource. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\d3d11_1_ddi_copy_flags.htm
old-project: display
ms.assetid: 044dc1cd-426e-4f6c-b14d-8c366834b5ac
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDI_COPY_DISCARD, D3D11_1DDI_COPY_NO_OVERWRITE, D3D11_1DDI_COPY_TILEABLE, D3D11_1_DDI_COPY_FLAGS, D3D11_1_DDI_COPY_FLAGS enumeration [Display Devices], d3d10umddi/D3D11_1DDI_COPY_DISCARD, d3d10umddi/D3D11_1DDI_COPY_NO_OVERWRITE, d3d10umddi/D3D11_1DDI_COPY_TILEABLE, d3d10umddi/D3D11_1_DDI_COPY_FLAGS, display.d3d11_1_ddi_copy_flags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D11_1_DDI_COPY_FLAGS
product: Windows
targetos: Windows
req.typenames: D3D11_1_DDI_COPY_FLAGS
---

# D3D11_1_DDI_COPY_FLAGS enumeration


## -description


Specifies how to handle the existing contents of a resource during a copy or update operation of a region within that resource. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -enum-fields




### -field D3D11_1DDI_COPY_NO_OVERWRITE

The caller guarantees that the portion of the surface that is being written to with new data is not currently being referenced or accessed by any previous render operation. The driver can take advantage of this capability to optimize performance and memory usage.


### -field D3D11_1DDI_COPY_DISCARD

The user-mode display driver can discard previous contents of the entire resource. The driver can take advantage of this capability to optimize performance and memory usage.


### -field D3D11_1DDI_COPY_TILEABLE

For tile-based deferred rendering, a copy operation can operate on only the currently processed tile in the source or destination resource, and the scene does not have to be flushed in all tiles.

