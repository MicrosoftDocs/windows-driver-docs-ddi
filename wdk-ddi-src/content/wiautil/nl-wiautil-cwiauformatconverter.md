---
UID: NL:wiautil.CWiauFormatConverter
title: CWiauFormatConverter (wiautil.h)
description: The CWiauFormatConverter class is a helper class for converting images to BMP format.
old-location: image\cwiauformatconverter_class.htm
tech.root: image
ms.assetid: b30c3336-ddc6-459d-97c4-244ca0b50cfc
ms.date: 05/03/2018
ms.keywords: CWiauFormatConverter, CWiauFormatConverter interface [Imaging Devices], CWiauFormatConverter interface [Imaging Devices],described, image.cwiauformatconverter_class, wiauFncs_8d01dc38-ef09-425a-ade6-d06bd0e1e08a.xml, wiautil/CWiauFormatConverter
ms.topic: class
req.header: wiautil.h
req.include-header: 
req.target-type: Windows
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
- wiautil.h
api_name:
- CWiauFormatConverter
product:
- Windows
targetos: Windows
req.typenames: 
---

# CWiauFormatConverter class


## -description


The <b>CWiauFormatConverter</b> class is a helper class for converting images to BMP format.


## -members

The <b>CWiauFormatConverter</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiauformatconverter-~cwiauformatconverter">~CWiauFormatConverter</a>
</td>
<td align="left" width="63%">
The <b>~CWiauFormatConverter</b> method is the destructor for the <b>CWiauFormatConverter</b> class.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiauformatconverter-converttobmp">ConvertToBmp</a>
</td>
<td align="left" width="63%">
The <b>ConvertToBmp</b> method converts an image to BMP format.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiauformatconverter-~cwiauformatconverter">CWiauFormatConverter</a>
</td>
<td align="left" width="63%">
The <b>CWiauFormatConverter</b> method is the constructor for the <b>CWiauFormatConverter</b> class.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/modem/ff541624(v=vs.85)">Init</a>
</td>
<td align="left" width="63%">
The <b>Init</b> method initializes the <b>CWiauFormatConverter</b> class and GDI+ for converting images. This method should be called only once.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiauformatconverter-isformatsupported">IsFormatSupported</a>
</td>
<td align="left" width="63%">
The <b>IsFormatSupported</b> method verifies that GDI+ supports the image format that is to be converted.

</td>
</tr>
</table> 

