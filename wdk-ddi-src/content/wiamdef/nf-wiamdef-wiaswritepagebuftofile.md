---
UID: NF:wiamdef.wiasWritePageBufToFile
title: wiasWritePageBufToFile function (wiamdef.h)
description: The wiasWritePageBufToFile function writes the contents of a temporary page buffer to an image file.
old-location: image\wiaswritepagebuftofile.htm
tech.root: image
ms.assetid: aa04ef8c-5b69-4d7e-8af4-8cbdb680a23a
ms.date: 05/03/2018
ms.keywords: image.wiaswritepagebuftofile, wiamdef/wiasWritePageBufToFile, wiasFncs_1d5b96b4-4737-481a-ae6a-e1ec4e8affef.xml, wiasWritePageBufToFile, wiasWritePageBufToFile function [Imaging Devices]
ms.topic: function
f1_keywords:
 - "wiamdef/wiasWritePageBufToFile"
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasWritePageBufToFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasWritePageBufToFile function

## -description

The **wiasWritePageBufToFile** function writes the contents of a temporary page buffer to an image file.

## -parameters

### -param pmdtc [in]

Pointer to a [MINIDRV_TRANSFER_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_minidrv_transfer_context) structure.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -remarks

The function writes data from a minidriver-allocated temporary page buffer to the image file opened by the WIA service. Minidrivers typically call this function after acquiring a page of data for which the minidriver allocated a temporary buffer.

This function is similar to [wiasWriteBufToFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritebuftofile), which can be used to write a buffer of image data to any type of image file. If a WIA minidriver intends to write a page of image data to a multipage TIFF file, including all appropriate tags, image file directory (IFD) entries, and other nonimage data, it should call this function, rather than **wiasWriteBufToFile**.

The expression *pmdtc*->*hFile* contains the handle to the file in TYMED_FILE (and TYMED_MULTIPAGE_FILE) transfers. This can be used to directly access the file that is being written to.

An example of how to use it is:

```cpp
SetFilePointer((HANDLE)(LONG_PTR)pmdtc->hFile,0,NULL,FILE_BEGIN);
if (!WriteFile((HANDLE)(LONG_PTR)pmdtc->hFile,
    pMyBuffer,
    dwNumBytesToWrite,
   &dwNumBytesWritten,
    NULL)) {
     //
     // Some error happened
     //
     .
     .
     .
    }
```

However, if you are considering using just the file handle in your TYMED_FILE and TYMED_MULTIPAGE_FILE transfers (to write data directly to the file using the file handle, instead of calling **wiasWritePageBufToFile**), use [wiasWriteBufToFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritebuftofile). This function performs the equivalent of:

```cpp
bRet = WriteFile((HANDLE)ULongToPtr(pmdtc->hFile),
    pmdtc->pTransferBuffer,
    pmdtc->lItemSize,
    &ulWritten,
    NULL);
```

This is essentially what you would do if you used the file handle directly. The advantage of the first example is that if the implementation was changed in a future release of WIA (for example, if the WIA service began using pipes instead of files, internally), the driver would not need to be updated.

## -see-also

[MINIDRV_TRANSFER_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_minidrv_transfer_context)

[wiasWriteBufToFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritebuftofile)

[wiasWritePageBufToStream](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritepagebuftostream)
