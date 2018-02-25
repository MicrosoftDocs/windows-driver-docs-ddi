---
UID: NF:wiautil.CWiauFormatConverter.IsFormatSupported
title: CWiauFormatConverter::IsFormatSupported method
author: windows-driver-content
description: The CWiauFormatConverter::IsFormatSupported method verifies that GDI+ supports the image format that is to be converted.
old-location: image\cwiauformatconverter_isformatsupported.htm
old-project: image
ms.assetid: 5bb69443-8ccd-4157-8815-fb3423b57e30
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, C, CWiauFormatConverter, CWiauFormatConverter interface [Imaging Devices], IsFormatSupported method, CWiauFormatConverter::IsFormatSupported, F, I, IsFormatSupported method [Imaging Devices], IsFormatSupported method [Imaging Devices], CWiauFormatConverter interface, IsFormatSupported,CWiauFormatConverter.IsFormatSupported, S, W, a, d, e, i, image.cwiauformatconverter_isformatsupported, m, n, o, p, r, s, t, u, v, wiauFncs_894f0261-249e-4b7c-aaa1-43a52bd48fbf.xml, wiautil/CWiauFormatConverter::IsFormatSupported"
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
-	CWiauFormatConverter.IsFormatSupported
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# CWiauFormatConverter::IsFormatSupported method


## -description


The <b>CWiauFormatConverter::IsFormatSupported</b> method verifies that GDI+ supports the image format that is to be converted.


## -syntax


````
BOOL IsFormatSupported(
   const GUID   pguidFormat
);
````


## -parameters




### -param pguidFormat

Points to the GUID of the format. The format GUIDs are defined in <i>gdiplusimaging.h</i>.


## -returns



The method returns <b>TRUE</b> if the format indicated by the format GUID is supported, and <b>FALSE</b> if it is not supported.




## -see-also

<a href="..\wiautil\nl-wiautil-cwiauformatconverter.md">CWiauFormatConverter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540369">CWiauFormatConverter::ConvertToBmp</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiauFormatConverter::IsFormatSupported method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

