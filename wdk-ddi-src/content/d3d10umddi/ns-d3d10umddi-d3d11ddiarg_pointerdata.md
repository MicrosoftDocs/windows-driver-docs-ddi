---
UID: NS:d3d10umddi.D3D11DDIARG_POINTERDATA
title: D3D11DDIARG_POINTERDATA
author: windows-driver-content
description: The D3D11DDIARG_POINTERDATA structure describes the location of the data that is reference by a class instance that has been assigned to an interface implementation.
old-location: display\d3d11ddiarg_pointerdata.htm
old-project: display
ms.assetid: 1065079d-ff48-4b68-930c-bbbd3f17d5bd
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11DDIARG_POINTERDATA, D3D11DDIARG_POINTERDATA
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
req.alt-api: D3D11DDIARG_POINTERDATA
req.alt-loc: d3d10umddi.h
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
req.typenames: D3D11DDIARG_POINTERDATA
---

# D3D11DDIARG_POINTERDATA structure



## -description
The D3D11DDIARG_POINTERDATA structure describes the location of the data that is reference by a class instance that has been assigned to an interface implementation. 



## -syntax

````
typedef struct D3D11DDIARG_POINTERDATA {
  UINT uCBOffset  :12;
  UINT uCBID  :4;
  UINT uBaseSamp  :4;
  UINT uBaseTex  :7;
  UINT uReserved  :5;
} D3D11DDIARG_POINTERDATA;
````


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
D3D11DDIARG_POINTERDATA contains the location of the data for one of the interfaces that is referred to in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">CsSetShaderWithIfaces</a>, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">DsSetShaderWithIfaces</a>, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">GsSetShaderWithIfaces</a>, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">HsSetShaderWithIfaces</a>, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">PsSetShaderWithIfaces</a>, or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">VsSetShaderWithIfaces</a> function. 


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">CsSetShaderWithIfaces</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">DsSetShaderWithIfaces</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">GsSetShaderWithIfaces</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">HsSetShaderWithIfaces</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">PsSetShaderWithIfaces</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">VsSetShaderWithIfaces</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_POINTERDATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

