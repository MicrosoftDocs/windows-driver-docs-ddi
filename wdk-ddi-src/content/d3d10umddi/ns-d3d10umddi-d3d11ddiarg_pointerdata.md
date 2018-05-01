---
UID: NS:d3d10umddi.D3D11DDIARG_POINTERDATA
title: D3D11DDIARG_POINTERDATA
author: windows-driver-content
description: The D3D11DDIARG_POINTERDATA structure describes the location of the data that is reference by a class instance that has been assigned to an interface implementation.
old-location: display\d3d11ddiarg_pointerdata.htm
old-project: display
ms.assetid: 1065079d-ff48-4b68-930c-bbbd3f17d5bd
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D11DDIARG_POINTERDATA, D3D11DDIARG_POINTERDATA structure [Display Devices], UMDisplayDriver_Dx11param_Structs_4e1d0abb-4385-4d8b-9687-0c913884ab46.xml, d3d10umddi/D3D11DDIARG_POINTERDATA, display.d3d11ddiarg_pointerdata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_POINTERDATA is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
api_name:
-	D3D11DDIARG_POINTERDATA
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_POINTERDATA
---

# D3D11DDIARG_POINTERDATA structure


## -description


The D3D11DDIARG_POINTERDATA structure describes the location of the data that is reference by a class instance that has been assigned to an interface implementation. 


## -struct-fields




### -field uCBOffset

A UINT value that specifies the offset, in bytes, into the constant buffer that the <b>uCBID</b> member specifies to reach the data for the interface. 

Setting this member is equivalent to setting the first 12 bits of a 32-bit value (0x00000FFF).


### -field uCBID

A UINT value that identifies the constant buffer that data for the interface is in. 

Setting this member is equivalent to setting bits 13 through 16 of a 32-bit value (0x0000F000).


### -field uBaseSamp

A UINT value that specifies the index of the first sampler that is used by the class instance of the interface implementation.

Setting this member is equivalent to setting bits 17 through 20 of a 32-bit value (0x000F0000).


### -field uBaseTex

A UINT value that specifies the index of the first texture that is used by the class instance of the interface implementation.

Setting this member is equivalent to setting bits 21 through 27 of a 32-bit value (0x07F00000).


### -field uReserved

Reserved for future use. This member makes the size of D3D11DDIARG_POINTERDATA 32-bit aligned and should always be set to zero. Setting this member to zero is equivalent to setting the remaining 5 bits (0xF8000000) of a 32-bit value to zeros.


## -remarks



D3D11DDIARG_POINTERDATA contains the location of the data for one of the interfaces that is referred to in a call to the driver's <a href="https://msdn.microsoft.com/2e7170e8-2b77-45a7-9ff5-834452c13ddf">CsSetShaderWithIfaces</a>, <a href="https://msdn.microsoft.com/fce9447a-459d-4446-9764-5b7daedce041">DsSetShaderWithIfaces</a>, <a href="https://msdn.microsoft.com/f1db3ed8-7621-4d3a-820d-f50298967404">GsSetShaderWithIfaces</a>, <a href="https://msdn.microsoft.com/c0dd4504-33d3-4a49-ac4e-169375f81430">HsSetShaderWithIfaces</a>, <a href="https://msdn.microsoft.com/8d8d4449-1770-4a57-b8b9-e1cfc64b96cb">PsSetShaderWithIfaces</a>, or <a href="https://msdn.microsoft.com/cc360e57-8c0a-441a-a072-7dc792ce201c">VsSetShaderWithIfaces</a> function. 




## -see-also




<a href="https://msdn.microsoft.com/2e7170e8-2b77-45a7-9ff5-834452c13ddf">CsSetShaderWithIfaces</a>



<a href="https://msdn.microsoft.com/fce9447a-459d-4446-9764-5b7daedce041">DsSetShaderWithIfaces</a>



<a href="https://msdn.microsoft.com/f1db3ed8-7621-4d3a-820d-f50298967404">GsSetShaderWithIfaces</a>



<a href="https://msdn.microsoft.com/c0dd4504-33d3-4a49-ac4e-169375f81430">HsSetShaderWithIfaces</a>



<a href="https://msdn.microsoft.com/8d8d4449-1770-4a57-b8b9-e1cfc64b96cb">PsSetShaderWithIfaces</a>



<a href="https://msdn.microsoft.com/cc360e57-8c0a-441a-a072-7dc792ce201c">VsSetShaderWithIfaces</a>
 

 

