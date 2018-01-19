---
UID: NF:prcomoem.IPrintOemUni.DownloadFontHeader
title: IPrintOemUni::DownloadFontHeader method
author: windows-driver-content
description: The IPrintOemUni::DownloadFontHeader method allows a rendering plug-in for Unidrv to send a font's header information to a printer.
old-location: print\iprintoemuni_downloadfontheader.htm
old-project: print
ms.assetid: 3d660d04-2872-44e6-ab76-719f5262bdd8
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUni, IPrintOemUni::DownloadFontHeader, DownloadFontHeader
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
req.alt-api: IPrintOemUni.DownloadFontHeader
req.alt-loc: prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni::DownloadFontHeader method



## -description
The <code>IPrintOemUni::DownloadFontHeader</code> method allows a rendering plug-in for <a href="wdkgloss.u#wdkgloss.unidrv#wdkgloss.unidrv"><i>Unidrv</i></a> to send a font's header information to a printer.



## -syntax

````
HRESULT DownloadFontHeader(
        PDEVOBJ     pdevobj,
        PUNIFONTOBJ pUFObj,
  [out] DWORD       *pdwResult
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param pUFObj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_unifontobj.md">UNIFONTOBJ</a> structure.


### -param pdwResult [out]

Receives a method-supplied value representing the amount of printer memory, in bytes, required to store the font header information. If the operation fails, the returned value should be zero.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
The <code>IPrintOemUni::DownloadFontHeader</code> method is used for supporting soft fonts on printers that do not accept <a href="wdkgloss.p#wdkgloss.pcl#wdkgloss.pcl"><i>PCL</i></a> commands. Its purpose is to allow a rendering plug-in to obtain font header information from Unidrv and to send the information to the printer.

Information that might be required for constructing a non-<a href="wdkgloss.p#wdkgloss.pcl#wdkgloss.pcl"><i>PCL</i></a> font header can be obtained by:

Referencing the <a href="..\printoem\ns-printoem-_unifontobj.md">UNIFONTOBJ</a> structure that is received as an input argument.

Calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function to get the font's <a href="https://msdn.microsoft.com/library/windows/hardware/ff565974">FONTOBJ</a> structure.

The method should send the header information to the spooler by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a>.

The <code>IPrintOemUni::DownloadFontHeader</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "DownloadFontHeader" as input.

If you implement the <code>IPrintOemUni::DownloadFontHeader</code> method, you must also implement the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554241">IPrintOemUni::DownloadCharGlyph</a> method.

For additional information see <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Customized Font Management</a>.</p>