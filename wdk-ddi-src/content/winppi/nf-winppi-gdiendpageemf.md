---
UID: NF:winppi.GdiEndPageEMF
title: GdiEndPageEMF function
author: windows-driver-content
description: The GdiEndPageEMF function ends EMF playback operations for a physical page of an EMF-formatted print job.
old-location: print\gdiendpageemf.htm
tech.root: print
ms.assetid: e15344a5-32ed-43a8-93c2-d5201617d595
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: GdiEndPageEMF, GdiEndPageEMF function [Print Devices], gdifnc_867f18b8-1764-41a4-a7c1-e43fa72a3d27.xml, print.gdiendpageemf, winppi/GdiEndPageEMF
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winppi.h
req.include-header: Winppi.h
req.target-type: Universal
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
req.lib: Gdi32.Lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll
-	GDI32Full.dll
api_name:
-	GdiEndPageEMF
product:
- Windows
targetos: Windows
req.typenames: 
---

# GdiEndPageEMF function


## -description


The <b>GdiEndPageEMF</b> function ends EMF playback operations for a physical page of an EMF-formatted print job.


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549517">GdiGetSpoolFileHandle</a>.


### -param dwOptimization

Caller-supplied flags. The following flag is defined:





#### EMF_PP_COLOR_OPTIMIZATION

Enable color optimization. For more information, see Remarks.


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>, and an error code can be obtained by calling <b>GetLastError</b>.




## -remarks



The <b>GdiEndPageEMF</b> function is exported by gdi32.dll for use within a print processor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560724">PrintDocumentOnPrintProcessor</a> function.

The <b>GdiEndPageEMF</b> function ends the processing of a physical page and causes it to be ejected from the printer. A print processor should call <b>GdiEndPageEMF</b> at the following times:

<ul>
<li>
After the appropriate number of document pages have been placed on the physical page by making calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549524">GdiPlayPageEMF</a>. Note that <b>GdiPlayPageEMF</b> does not actually print on the device context, but instead prepares a data structure that describes the text and graphics that are to be printed on the physical page(s). The text and graphics are printed to the device context when <b>GdiEndPageEMF</b> is called.

</li>
<li>
Whenever a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549478">GdiGetDevmodeForPage</a> indicates a document page's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure is different from the previous page's DEVMODE structure.

</li>
</ul>
If this function is called with the <i>dwOptimization </i>parameter set to EMF_PP_COLOR_OPTIMIZATION, color optimization is enabled. If <i>dwOptimization</i> is set to 0, no optimization is performed. When color optimization is enabled, the presence of color in the spool file causes the spool file to be played in color; the lack of color in the spool file causes the spool file to be played in monochrome.

If you are creating a Unidrv rendering plug-in to generate color watermarks, be advised that color optimization causes color watermarks to be printed in black and white when they are printed on black-and-white documents. To ensure that color watermarks print correctly with color and black-and-white documents, disable color optimization.

The color optimization controlled by the <i>dwOptimization</i> parameter can also be controlled by setting the <b>dwColorOptimization</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545091">ATTRIBUTE_INFO_2</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545093">ATTRIBUTE_INFO_3</a> structures. This optimization also can be controlled by the Unidrv *<b>ChangeColorModeOnDoc?</b> color attribute (see <a href="https://msdn.microsoft.com/c8de0186-9cf5-43e5-81e7-33351a34c13c">Color Attributes</a>).

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549524">GdiPlayPageEMF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549543">GdiStartPageEMF</a>
 

 

