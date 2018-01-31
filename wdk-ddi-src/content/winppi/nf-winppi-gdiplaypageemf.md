---
UID: NF:winppi.GdiPlayPageEMF
title: GdiPlayPageEMF function
author: windows-driver-content
description: The GdiPlayPageEMF function plays the EMF records within a specified rectangle for one document page of a spooled print job.
old-location: print\gdiplaypageemf.htm
old-project: print
ms.assetid: e0122858-0c9d-4aa8-a394-89d65fb98fda
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: winppi/GdiPlayPageEMF, print.gdiplaypageemf, GdiPlayPageEMF function [Print Devices], gdifnc_b1c27aba-d367-481a-8012-6c2f957ff11e.xml, GdiPlayPageEMF
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll
-	GDI32Full.dll
apiname:
-	GdiPlayPageEMF
product: Windows
targetos: Windows
req.typenames: "*PDOT11_WPS_DEVICE_NAME, DOT11_WPS_DEVICE_NAME"
req.product: Windows 10 or later.
---

# GdiPlayPageEMF function


## -description


The <b>GdiPlayPageEMF</b> function plays the EMF records within a specified rectangle for one document page of a spooled print job.


## -syntax


````
BOOL GdiPlayPageEMF(
   HANDLE SpoolFileHandle,
   HANDLE hemf,
   RECT   *prectDocument,
   RECT   *prectBorder,
   RECT   *prectClip
);
````


## -parameters




#### - SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>.


#### - hemf

Caller-supplied page handle, obtained by calling <a href="..\winppi\nf-winppi-gdigetpagehandle.md">GdiGetPageHandle</a>, identifying the page for which records are to be played.


#### - prectDocument

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure specifying the rectangle into which the page is to be drawn.


#### - prectBorder

Caller-supplied pointer to a RECT structure specifying the page's border rectangle (if any). Can be <b>NULL</b>.


#### - prectClip

Caller-supplied pointer to a RECT structure specifying the coordinates of the page's clip region (if any). Can be <b>NULL</b>.


## -returns


If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>, and an error code can be obtained by calling <b>GetLastError</b>.



## -remarks


The <b>GdiPlayPageEMF</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

The <b>GdiPlayPageEMF</b> function is the means by which a print processor positions a document page or a specified rectangular region of a document page on a physical page. Note that <b>GdiPlayPageEMF</b> does not actually print on the device context, but instead prepares a data structure that describes the text and graphics that are to be printed on the physical page(s). The text and graphics are printed to the device context when <a href="..\winppi\nf-winppi-gdiendpageemf.md">GdiEndPageEMF</a> is called.

The print processor uses <i>prectClip</i> to describe the rectangular region to be printed, and <i>prectDocument</i> to describe a rectangle into which the document page (or clipped region) must fit. If<i> prectClip</i> is <b>NULL</b>, the entire document page will be printed. For non-<b>NULL</b> values of <i>prectClip</i>, only the portion of the document page within the clip region will be printed. The <b>GdiPlayPageEMF</b> function then performs the scaling and translation operations required to make the document page (or selected portion) fit into the rectangle.

The <i>prectBorder</i> parameter, if it is non-<b>NULL</b>, describes a solid-line border rectangle to be drawn around the document page. If <i>prectBorder</i> is <b>NULL</b>, no such border will be drawn.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.



## -see-also

<a href="..\winppi\nf-winppi-gdiendpageemf.md">GdiEndPageEMF</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GdiPlayPageEMF function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

