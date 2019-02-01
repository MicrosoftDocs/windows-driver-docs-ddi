---
UID: NS:d3dkmddi._DXGK_CREATEDEVICEFLAGS
title: _DXGK_CREATEDEVICEFLAGS (d3dkmddi.h)
description: The DXGK_CREATEDEVICEFLAGS structure identifies how to create devices.
old-location: display\dxgk_createdeviceflags.htm
ms.assetid: 31dc1493-a7c9-4ca0-b718-98224d9c5675
ms.date: 05/10/2018
ms.keywords: DXGK_CREATEDEVICEFLAGS, DXGK_CREATEDEVICEFLAGS structure [Display Devices], DmStructs_f8513fe3-ce39-4555-a667-20ff383583fc.xml, _DXGK_CREATEDEVICEFLAGS, d3dkmddi/DXGK_CREATEDEVICEFLAGS, display.dxgk_createdeviceflags
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	d3dkmddi.h
api_name:
-	DXGK_CREATEDEVICEFLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_CREATEDEVICEFLAGS
---

# _DXGK_CREATEDEVICEFLAGS structure


## -description


The DXGK_CREATEDEVICEFLAGS structure identifies how to create devices.


## -struct-fields




### -field SystemDevice

A UINT value that specifies whether devices that the driver's <a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a> function creates are system devices.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field GdiDevice

A UINT value that specifies whether the devices that the driver's <a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a> function creates are GDI-specific devices.

Setting this member is equivalent to setting the second bit of the 32-bit Value member (0x00000002).

This member is available beginning with Windows 7.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting bits 3 through 31 (0x7FFFFFFC) of the 32-bit <b>Value</b> member to zeros.


### -field DXGK_DEVICE_RESERVED0

Supported beginning with Windows 8.

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the last bit (0x80000000) of the 32-bit <b>Value</b> member to zero.


### -field Value

A member in the union that DXGK_CREATEDEVICEFLAGS contains that can hold a 32-bit value that identifies how to create devices.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557570">DXGKARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a>
 

 

