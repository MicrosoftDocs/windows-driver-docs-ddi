---
UID: NF:wiamdef.wiasWriteBufToFile
title: wiasWriteBufToFile function
author: windows-driver-content
description: The wiasWriteBufToFile function writes from a specified buffer to an image file.
old-location: image\wiaswritebuftofile.htm
old-project: image
ms.assetid: 29e9fa32-9264-41d7-8ac2-c6a08cab2880
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: wiasWriteBufToFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: wiasWriteBufToFile
req.alt-loc: Wiaservc.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
req.typenames: *PDEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, DEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# wiasWriteBufToFile function



## -description
The <b>wiasWriteBufToFile</b> function writes from a specified buffer to an image file.



## -syntax

````
HRESULT _stdcall wiasWriteBufToFile(
       LONG                      lFlags,
  _In_ PMINIDRV_TRANSFER_CONTEXT pmdtc
);
````


## -parameters

### -param lFlags 

Specifies a set of operation flags. This parameter should be set to 0.


### -param pmdtc [in]

Pointer to a <a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a> structure.


## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).


## -remarks
A WIA minidriver uses this function to write a buffer to any type of image file. A driver that intends to write a page of purely image data to a multipage TIFF file, delegating the addition of the appropriate tags, image file directory (IFD) entries, and other nonimage data to the WIA service, should use <a href="..\wiamdef\nf-wiamdef-wiaswritepagebuftofile.md">wiasWritePageBufToFile</a>.


## -see-also
<dl>
<dt>
<a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswritepagebuftofile.md">wiasWritePageBufToFile</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswritepagebuftostream.md">wiasWritePageBufToStream</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasWriteBufToFile function%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

