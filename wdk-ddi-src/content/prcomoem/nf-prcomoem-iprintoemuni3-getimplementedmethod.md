---
UID: NF:prcomoem.IPrintOemUni3.GetImplementedMethod
title: IPrintOemUni3::GetImplementedMethod (prcomoem.h)
description: The IPrintOemUni3::GetImplementedMethod method is used by Unidrv to determine which IPrintOemUni interface methods a rendering plug-in has implemented.
old-location: print\iprintoemuni3_getimplementedmethod.htm
tech.root: print
ms.assetid: a1de8e8f-eca1-4630-b689-585027184a08
ms.date: 04/20/2018
keywords: ["IPrintOemUni3::GetImplementedMethod"]
ms.keywords: GetImplementedMethod, GetImplementedMethod method [Print Devices], GetImplementedMethod method [Print Devices],IPrintOemUni3 interface, IPrintOemUni3 interface [Print Devices],GetImplementedMethod method, IPrintOemUni3.GetImplementedMethod, IPrintOemUni3::GetImplementedMethod, prcomoem/IPrintOemUni3::GetImplementedMethod, print.iprintoemuni3_getimplementedmethod, print_unidrv-pscript_rendering_7ca27745-8b8c-49c6-a80f-06bdc67132d5.xml
f1_keywords:
 - "prcomoem/IPrintOemUni3.GetImplementedMethod"
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
- Prcomoem.h
api_name:
- IPrintOemUni3.GetImplementedMethod
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni3::GetImplementedMethod


## -description


The <code>IPrintOemUni3::GetImplementedMethod</code> method is used by Unidrv to determine which <b>IPrintOemUni</b> interface methods a rendering plug-in has implemented.


## -parameters




### -param pMethodName

Caller-supplied pointer to a string that represents the name of an <b>IPrintOemUni</b> interface method, such as "ImageProcessing" for <b>IPrintOemUni3::ImageProcessing</b> or "FilterGraphics" for <b>IPrintOemUni3::FilterGraphics</b>.


## -returns



<code>GetImplementedMethod</code> must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded (that is, the specified method is implemented).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The operation failed (that is, the specified method is not implemented).

</td>
</tr>
</table>
 




## -remarks



A rendering plug-in for Unidrv must implement the <code>IPrintOemUni3::GetImplementedMethod</code> method, together with several other methods in this interface. For those methods that are optional, <code>IPrintOemUni3::GetImplementedMethod</code> examines the input method name string and returns a value that indicates whether the associated method is implemented within the plug-in. For example, if <code>IPrintOemUni3::GetImplementedMethod</code> is called with the string "ImageProcessing", it should return S_OK if the <b>IPrintOemUni3::ImageProcessing</b> method is implemented and S_FALSE otherwise.  

The <code>IPrintOemUni3::GetImplementedMethod</code> method must recognize the following name strings:

"CommandCallback"

"Compression"

"DownloadCharGlyph"

"DownloadFontHeader"

"DownloadPattern"

"FilterGraphics"

"GetPDEVAdjustment"

"HalftonePattern"

"ImageProcessing"

"MemoryUsage"

"OutputCharStr"

"SendFontCmd"

"SetBandSize"

"TextOutAsBitmap"

"TTDownloadMethod"

"TTYGetInfo"

"WritePrinter"



