---
UID: NS:printoem._GETINFO_GLYPHBITMAP
title: _GETINFO_GLYPHBITMAP
author: windows-driver-content
description: The GETINFO_GLYPHBITMAP structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_glyphbitmap.htm
old-project: print
ms.assetid: 6a5887fd-0269-4cd1-acf1-f7242016d993
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _GETINFO_GLYPHBITMAP, *PGETINFO_GLYPHBITMAP, GETINFO_GLYPHBITMAP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GETINFO_GLYPHBITMAP
req.alt-loc: printoem.h
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
req.typenames: *PGETINFO_GLYPHBITMAP, GETINFO_GLYPHBITMAP
req.product: Windows 10 or later.
---

# _GETINFO_GLYPHBITMAP structure



## -description
The GETINFO_GLYPHBITMAP structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.



## -syntax

````
typedef struct _GETINFO_GLYPHBITMAP {
  DWORD     dwSize;
  HGLYPH    hGlyph;
  GLYPHDATA *pGlyphData;
} GETINFO_GLYPHBITMAP, *PGETINFO_GLYPHBITMAP;
````


## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the GETINFO_GLYPHBITMAP structure. Supplied by <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field hGlyph

Handle to the glyph. See the following Remarks section. Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field pGlyphData

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566819">GLYPHDATA</a> structure. The structure is filled in by Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function. The pointer is supplied by the <i>UNIFONTOBJ_GetInfo</i> caller.


## -remarks
To obtain a glyph bitmap, a rendering plug-in can supply the address of a GETINFO_GLYPHBITMAP structure when calling Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.

The value that a rendering plug-in specifies for the <b>hGlyph</b> member must have been previously received as the <i>hGlyph</i> parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554241">IPrintOemUni::DownloadCharGlyph</a> method.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566819">GLYPHDATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554241">IPrintOemUni::DownloadCharGlyph</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GETINFO_GLYPHBITMAP structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

