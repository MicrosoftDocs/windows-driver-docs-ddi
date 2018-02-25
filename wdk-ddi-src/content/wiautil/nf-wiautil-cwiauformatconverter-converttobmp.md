---
UID: NF:wiautil.CWiauFormatConverter.ConvertToBmp
title: CWiauFormatConverter::ConvertToBmp method
author: windows-driver-content
description: The CWiauFormatConverter::ConvertToBmp method converts an image to BMP format.
old-location: image\cwiauformatconverter_converttobmp.htm
old-project: image
ms.assetid: 9ac85fe9-bc44-4a70-9619-bb13e878bb49
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, B, C, CWiauFormatConverter, CWiauFormatConverter interface [Imaging Devices], ConvertToBmp method, CWiauFormatConverter::ConvertToBmp, ConvertToBmp method [Imaging Devices], ConvertToBmp method [Imaging Devices], CWiauFormatConverter interface, ConvertToBmp,CWiauFormatConverter.ConvertToBmp, F, T, W, a, e, i, image.cwiauformatconverter_converttobmp, m, n, o, p, r, t, u, v, wiauFncs_2c929e01-3e1f-4a07-9f2f-f50775b39017.xml, wiautil/CWiauFormatConverter::ConvertToBmp"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
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
req.lib: wiautil.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wiautil.h
apiname:
-	CWiauFormatConverter.ConvertToBmp
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# CWiauFormatConverter::ConvertToBmp method


## -description


The <b>CWiauFormatConverter::ConvertToBmp</b> method converts an image to BMP format.


## -syntax


````
HRESULT ConvertToBmp(
   BYTE           *pSource,
   INT            iSourceSize,
   BYTE           **ppDest,
   INT            *piDestSize,
   BMP_IMAGE_INFO *pBmpImageInfo,
   SKIP_AMOUNT    iSkipAmt = SKIP_OFF

);
````


## -parameters




### -param pSource

Points to the memory location containing the first byte of the source image.


### -param iSourceSize

Specifies the size, in bytes, of the source image.


### -param ppDest

Pointer to a memory location that receives the address of the resulting image.


### -param piDestSize

Pointer to a memory location that receives the size, in bytes, of the resulting image.


### -param pBmpImageInfo

Pointer to a <a href="..\wiautil\ns-wiautil-_bmp_image_info.md">BMP_IMAGE_INFO</a> structure that receives information about the resulting image.


### -param iSkipAmt






#### - iSkipAmt = SKIP_OFF

<i>Optional</i>. Specifies the amount of the BMP header to skip. The default value of this parameter denotes that none of the BMP header is skipped.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error.




## -remarks



The caller of this method can pass a result buffer in <i>ppDest</i> and the size in <i>piDestSize</i>. Alternatively, the caller can set *<i>ppDest</i> to <b>NULL</b> and *<i>piDestSize</i> to zero in the call to indicate that this method should allocate the memory. The caller is responsible for freeing the memory using the <b>delete []</b> operator.




## -see-also

<a href="..\wiautil\nl-wiautil-cwiauformatconverter.md">CWiauFormatConverter</a>



<a href="..\wiautil\ns-wiautil-_bmp_image_info.md">BMP_IMAGE_INFO</a>



<a href="..\wiautil\ne-wiautil-skip_amount.md">SKIP_AMOUNT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540379">CWiauFormatConverter::IsFormatSupported</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiauFormatConverter::ConvertToBmp method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

