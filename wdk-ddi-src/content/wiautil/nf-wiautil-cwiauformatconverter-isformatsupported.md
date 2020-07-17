---
UID: NF:wiautil.CWiauFormatConverter.IsFormatSupported
title: CWiauFormatConverter::IsFormatSupported (wiautil.h)
description: The CWiauFormatConverter::IsFormatSupported method verifies that GDI+ supports the image format that is to be converted.
old-location: image\cwiauformatconverter_isformatsupported.htm
tech.root: image
ms.assetid: 5bb69443-8ccd-4157-8815-fb3423b57e30
ms.date: 05/03/2018
keywords: ["CWiauFormatConverter::IsFormatSupported"]
ms.keywords: CWiauFormatConverter interface [Imaging Devices],IsFormatSupported method, CWiauFormatConverter.IsFormatSupported, CWiauFormatConverter::IsFormatSupported, IsFormatSupported, IsFormatSupported method [Imaging Devices], IsFormatSupported method [Imaging Devices],CWiauFormatConverter interface, image.cwiauformatconverter_isformatsupported, wiauFncs_894f0261-249e-4b7c-aaa1-43a52bd48fbf.xml, wiautil/CWiauFormatConverter::IsFormatSupported
f1_keywords:
 - "wiautil/CWiauFormatConverter.IsFormatSupported"
 - "CWiauFormatConverter.IsFormatSupported"
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wiautil.h
api_name:
- CWiauFormatConverter.IsFormatSupported
product:
- Windows
targetos: Windows
req.typenames: 
---

# CWiauFormatConverter::IsFormatSupported


## -description


The <b>CWiauFormatConverter::IsFormatSupported</b> method verifies that GDI+ supports the image format that is to be converted.


## -parameters




### -param pguidFormat

Points to the GUID of the format. The format GUIDs are defined in <i>gdiplusimaging.h</i>.


## -returns



The method returns <b>TRUE</b> if the format indicated by the format GUID is supported, and <b>FALSE</b> if it is not supported.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540363(v=vs.85)">CWiauFormatConverter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-cwiauformatconverter-converttobmp">CWiauFormatConverter::ConvertToBmp</a>
 

 

