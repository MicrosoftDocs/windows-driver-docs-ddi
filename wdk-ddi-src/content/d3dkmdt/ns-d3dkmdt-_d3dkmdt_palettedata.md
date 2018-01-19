---
UID: NS:d3dkmdt._D3DKMDT_PALETTEDATA
title: _D3DKMDT_PALETTEDATA
author: windows-driver-content
description: The D3DKMDT_PALETTEDATA structure describes a palette entry for the display.
old-location: display\d3dkmdt_palettedata.htm
old-project: display
ms.assetid: 81ff56bb-84e5-4556-a0bf-32164b938622
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMDT_PALETTEDATA, D3DKMDT_PALETTEDATA
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
req.alt-api: D3DKMDT_PALETTEDATA
req.alt-loc: d3dkmdt.h
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
req.typenames: D3DKMDT_PALETTEDATA
---

# _D3DKMDT_PALETTEDATA structure



## -description
The D3DKMDT_PALETTEDATA structure describes a palette entry for the display.



## -syntax

````
typedef struct _D3DKMDT_PALETTEDATA {
  BYTE Red;
  BYTE Green;
  BYTE Blue;
  BYTE Unused;
} D3DKMDT_PALETTEDATA;
````


## -struct-fields

### -field Red

An 8-bit value for the red portion of the color registers.


### -field Green

An 8-bit value for the green portion of the color registers.


### -field Blue

An 8-bit value for the blue portion of the color registers.


### -field Unused

An unused portion of the display.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkarg_setpalette.md">DXGKARG_SETPALETTE</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpalette.md">DxgkDdiSetPalette</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_PALETTEDATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

