---
UID: NS:d3dumddi.D3DDDIARG_UPDATESUBRESOURCEUP
title: D3DDDIARG_UPDATESUBRESOURCEUP
author: windows-driver-content
description: Describes info that's used to update a destination subresource region from a source system-memory region. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\d3dddiarg_updatesubresourceup.htm
tech.root: display
ms.assetid: 27BE493F-8F70-4FBF-AA58-D6ACB27BFC2D
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDIARG_UPDATESUBRESOURCEUP, D3DDDIARG_UPDATESUBRESOURCEUP structure [Display Devices], d3dumddi/D3DDDIARG_UPDATESUBRESOURCEUP, display.d3dddiarg_updatesubresourceup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dumddi.h
api_name:
-	D3DDDIARG_UPDATESUBRESOURCEUP
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_UPDATESUBRESOURCEUP
---

# D3DDDIARG_UPDATESUBRESOURCEUP structure


## -description


Describes info that's used to update a destination subresource region from a source system-memory region. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -struct-fields




### -field hResource

A handle to the destination resource to copy to.


### -field SubResourceIndex

The index of the destination subresource to which data is to be copied.


### -field DstBox

A destination region, of type  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451148">D3DDDIBOX</a>, of the subresource to which data is to be copied. If <b>Flags</b>-&gt;<a href="https://msdn.microsoft.com/DA114D60-60EE-4D1D-B42C-A84CE54C8B95">BoxValid</a> is not set, the entire subresource must be updated.


### -field pSysMemUP

A pointer to the beginning address of the source data that the <a href="https://msdn.microsoft.com/5AF55FED-6FD6-41BE-A743-1E9D0EA51C9C">pfnUpdateSubresourceUP</a> function copies to update the destination subresouce.


### -field RowPitch

The offset, in bytes, to move to the next row of source data.


### -field DepthPitch

The offset, in bytes, to move to the next depth slice of source data.


### -field Flags

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn449151">D3DDDIARG_COPYFLAGS</a> structure that specifies additional characteristics of the subresource update operation.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn449151">D3DDDIARG_COPYFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451148">D3DDDIBOX</a>



<a href="https://msdn.microsoft.com/5AF55FED-6FD6-41BE-A743-1E9D0EA51C9C">pfnUpdateSubresourceUP</a>
 

 

