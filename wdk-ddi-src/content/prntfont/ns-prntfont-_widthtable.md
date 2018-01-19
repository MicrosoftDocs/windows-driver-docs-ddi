---
UID: NS:prntfont._WIDTHTABLE
title: _WIDTHTABLE
author: windows-driver-content
description: The WIDTHTABLE structure is used to define the contents of Unidrv font metrics files (.ufm files).
old-location: print\widthtable.htm
old-project: print
ms.assetid: 6c7b35a2-f9fd-41a9-a353-ec8b78259bf0
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _WIDTHTABLE, WIDTHTABLE, *PWIDTHTABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: prntfont.h
req.include-header: Prntfont.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WIDTHTABLE
req.alt-loc: prntfont.h
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
req.typenames: WIDTHTABLE, *PWIDTHTABLE
req.product: Windows 10 or later.
---

# _WIDTHTABLE structure



## -description
The WIDTHTABLE structure is used to define the contents of <a href="print.customized_font_management#ddk_unidrv_font_metrics_files_gg#ddk_unidrv_font_metrics_files_gg">Unidrv font metrics files</a> (.ufm files).



## -syntax

````
typedef struct _WIDTHTABLE {
  DWORD    dwSize;
  DWORD    dwRunNum;
  WIDTHRUN WidthRun[1];
} WIDTHTABLE, *PWIDTHTABLE;
````


## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the WIDTHTABLE structure, including the <b>WidthRun</b> array.


### -field dwRunNum

Specifies the number of elements in the <b>WidthRun</b> array.


### -field WidthRun

Is an array of <a href="..\prntfont\ns-prntfont-_widthrun.md">WIDTHRUN</a> structures.


## -remarks
A .ufm file's WIDTHTABLE structure, which describes character widths, is accessed by a pointer in the file's <a href="..\prntfont\ns-prntfont-_unifm_hdr.md">UNIFM_HDR</a> structure.


## -see-also
<dl>
<dt>
<a href="..\prntfont\ns-prntfont-_widthrun.md">WIDTHRUN</a>
</dt>
<dt>
<a href="..\prntfont\ns-prntfont-_unifm_hdr.md">UNIFM_HDR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WIDTHTABLE structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

