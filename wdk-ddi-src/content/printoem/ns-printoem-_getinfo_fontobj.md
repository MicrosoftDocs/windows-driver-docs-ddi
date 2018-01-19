---
UID: NS:printoem._GETINFO_FONTOBJ
title: _GETINFO_FONTOBJ
author: windows-driver-content
description: The GETINFO_FONTOBJ structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_fontobj.htm
old-project: print
ms.assetid: f5116986-aa0c-4cc3-9893-c93e83e922f7
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _GETINFO_FONTOBJ, *PGETINFO_FONTOBJ, GETINFO_FONTOBJ
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
req.alt-api: GETINFO_FONTOBJ
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
req.typenames: *PGETINFO_FONTOBJ, GETINFO_FONTOBJ
req.product: Windows 10 or later.
---

# _GETINFO_FONTOBJ structure



## -description
The GETINFO_FONTOBJ structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.



## -syntax

````
typedef struct _GETINFO_FONTOBJ {
  DWORD   dwSize;
  FONTOBJ *pFontObj;
} GETINFO_FONTOBJ, *PGETINFO_FONTOBJ;
````


## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the GETINFO_FONTOBJ structure. Supplied by the UNIFONTOBJ_GetInfo caller.


### -field pFontObj

Pointer to an empty <a href="https://msdn.microsoft.com/library/windows/hardware/ff565974">FONTOBJ</a> structure. The structure is filled in by Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function. The pointer is supplied by the UNIFONTOBJ_GetInfo caller.


## -remarks
To obtain a font's FONTOBJ structure contents, a rendering plug-in can supply the address of a GETINFO_FONTOBJ structure when calling Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565974">FONTOBJ</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GETINFO_FONTOBJ structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

