---
UID: NF:prcomoem.IPrintOemUni2.GetImplementedMethod
title: IPrintOemUni2::GetImplementedMethod (prcomoem.h)
description: The IPrintOemUni2::GetImplementedMethod method is used by Unidrv to determine which IPrintOemUni2 interface methods a rendering plug-in has implemented.
old-location: print\iprintoemuni2_getimplementedmethod.htm
tech.root: print
ms.assetid: a26f7094-8530-4525-b94a-c94dc9ba9629
ms.date: 04/20/2018
keywords: ["IPrintOemUni2::GetImplementedMethod"]
ms.keywords: GetImplementedMethod, GetImplementedMethod method [Print Devices], GetImplementedMethod method [Print Devices],IPrintOemUni2 interface, IPrintOemUni2 interface [Print Devices],GetImplementedMethod method, IPrintOemUni2.GetImplementedMethod, IPrintOemUni2::GetImplementedMethod, prcomoem/IPrintOemUni2::GetImplementedMethod, print.iprintoemuni2_getimplementedmethod, print_unidrv-pscript_rendering_3d4fda36-1657-4656-a0bd-e9f65f0f5982.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintOemUni2::GetImplementedMethod
 - prcomoem/IPrintOemUni2::GetImplementedMethod
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintOemUni2.GetImplementedMethod
---

# IPrintOemUni2::GetImplementedMethod


## -description

The <code>IPrintOemUni2::GetImplementedMethod</code> method is used by Unidrv to determine which <b>IPrintOemUni2</b> interface methods a rendering plug-in has implemented.

## -parameters

### -param pMethodName

Caller-supplied pointer to a string that represents the name of an <b>IPrintOemUni2</b> interface method, such as "ImageProcessing" for <b>IPrintOemUni2::ImageProcessing</b> or "FilterGraphics" for <b>IPrintOemUni2::FilterGraphics</b>.

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

A rendering plug-in for Unidrv must implement the <code>IPrintOemUni2::GetImplementedMethod</code> method, together with several other methods in this interface. For those methods that are optional, <code>IPrintOemUni2::GetImplementedMethod</code> examines the input method name string and returns a value that indicates whether the associated method is implemented within the plug-in. For example, if <code>IPrintOemUni2::GetImplementedMethod</code> is called with the string "ImageProcessing", it should return S_OK if the <b>IPrintOemUni2::ImageProcessing</b> method is implemented and S_FALSE otherwise.  

The <code>IPrintOemUni2::GetImplementedMethod</code> method must recognize the following name strings:

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

"WritePrinter"

