---
UID: NF:prcomoem.IPrintOemUni.GetImplementedMethod
title: IPrintOemUni::GetImplementedMethod method
author: windows-driver-content
description: The IPrintOemUni::GetImplementedMethod method is used by Unidrv to determine which IPrintOemUni interface methods a rendering plug-in has implemented.
old-location: print\iprintoemuni_getimplementedmethod.htm
old-project: print
ms.assetid: bc2a00ea-214a-435a-86fa-d694188d0245
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetImplementedMethod method [Print Devices], GetImplementedMethod method [Print Devices], IPrintOemUni interface, GetImplementedMethod,IPrintOemUni.GetImplementedMethod, IPrintOemUni, IPrintOemUni interface [Print Devices], GetImplementedMethod method, IPrintOemUni::GetImplementedMethod, prcomoem/IPrintOemUni::GetImplementedMethod, print.iprintoemuni_getimplementedmethod, print_unidrv-pscript_rendering_904bb300-cb68-4386-a5d1-9e614b38651d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemUni.GetImplementedMethod
product:
- Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni::GetImplementedMethod method


## -description


The <code>IPrintOemUni::GetImplementedMethod</code> method is used by Unidrv to determine which <b>IPrintOemUni</b> interface methods a rendering plug-in has implemented.


## -parameters




### -param pMethodName

Caller-supplied pointer to a string that represents the name of an <b>IPrintOemUni</b> interface method, such as "ImageProcessing" for <b>IPrintOemUni::ImageProcessing</b> or "FilterGraphics" for <b>IPrintOemUni::FilterGraphics</b>.


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



A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::GetImplementedMethod</code> method, together with several other methods in this interface. For those methods that are optional, <code>IPrintOemUni::GetImplementedMethod</code> examines the input method name string and returns a value that indicates whether the associated method is implemented within the plug-in. For example, if <code>IPrintOemUni::GetImplementedMethod</code> is called with the string "ImageProcessing", it should return S_OK if the <b>IPrintOemUni::ImageProcessing </b>method is implemented and S_FALSE otherwise.  

The <code>IPrintOemUni::GetImplementedMethod</code> method must recognize the following name strings:

"CommandCallback"

"Compression"

"DownloadCharGlyph"

"DownloadFontHeader"

"FilterGraphics"

"HalftonePattern"

"ImageProcessing"

"MemoryUsage"

"OutputCharStr"

"SendFontCmd"

"TextOutAsBitmap"

"TTDownloadMethod"

"TTYGetInfo"



