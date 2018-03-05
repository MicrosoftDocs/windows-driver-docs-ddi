---
UID: NF:wiamdef.wiasWritePageBufToStream
title: wiasWritePageBufToStream function
author: windows-driver-content
description: The wiasWritePageBufToStream function writes the contents of a temporary page buffer to the IStream interface provided by the application.
old-location: image\wiaswritepagebuftostream.htm
old-project: image
ms.assetid: f8f8ac2a-705e-426c-8c4a-00581b8d1dfe
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: image.wiaswritepagebuftostream, wiamdef/wiasWritePageBufToStream, wiasFncs_1173cf4b-d42c-4c6b-959e-68f456b78ec4.xml, wiasWritePageBufToStream, wiasWritePageBufToStream function [Imaging Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Wiaservc.dll
api_name:
-	wiasWritePageBufToStream
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# wiasWritePageBufToStream function


## -description


The <b>wiasWritePageBufToStream</b> function writes the contents of a temporary page buffer to the <b>IStream</b> interface provided by the application.


## -syntax


````
HRESULT _stdcall wiasWritePageBufToStream(
  _In_ PMINIDRV_TRANSFER_CONTEXT pmdtc,
  _In_ IStream                   *pstream
);
````


## -parameters




### -param pmdtc [in]

Pointer to a <a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a> structure.


### -param pstream [in]

Pointer to the <b>IStream</b> data stream provided by the application. The <b>IStream</b> interface is described in the Microsoft Windows SDK documentation.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_<i>XXX</i> errors (described in the Windows SDK documentation).




## -remarks



The function writes data from a temporary page buffer that is allocated by a minidriver to the image data stream provided by the calling application. Minidrivers typically call this function after acquiring a page of data for which the minidriver allocated a temporary buffer.

This function is similar to <a href="..\wiamdef\nf-wiamdef-wiaswritebuftofile.md">wiasWriteBufToFile</a> and <a href="..\wiamdef\nf-wiamdef-wiaswritepagebuftofile.md">wiasWritePageBufToFile</a>. The <b>wiasWriteBufToFile </b>function can be used to write a buffer of image data to any type of image file. The <b>wiasWritePageBufToFile</b> function can be used to write a page of image data to a multipage TIFF file with all appropriate tags and image file directory (IFD) entries. If the driver intends to write this multipage TIFF file data to a stream, it would call <b>wiasWritePageBufToStream</b>.




## -see-also

<a href="..\wiamdef\nf-wiamdef-wiaswritepagebuftofile.md">wiasWritePageBufToFile</a>



<a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a>



<a href="..\wiamdef\nf-wiamdef-wiaswritebuftofile.md">wiasWriteBufToFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasWritePageBufToStream function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

