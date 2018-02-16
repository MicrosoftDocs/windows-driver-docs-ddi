---
UID: NF:prcomoem.IPrintOemUni3.DownloadPattern
title: IPrintOemUni3::DownloadPattern method
author: windows-driver-content
description: The IPrintOemUni3::DownloadPattern method downloads a pattern to a printer.
old-location: print\iprintoemuni3_downloadpattern.htm
old-project: print
ms.assetid: 7604a6df-c73a-4114-916f-1e777a323731
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.iprintoemuni3_downloadpattern, DownloadPattern method [Print Devices], IPrintOemUni3 interface, IPrintOemUni3 interface [Print Devices], DownloadPattern method, DownloadPattern, print_unidrv-pscript_rendering_ce79f65e-3515-4d0b-96d6-d468c15039f1.xml, IPrintOemUni3::DownloadPattern, prcomoem/IPrintOemUni3::DownloadPattern, IPrintOemUni3, DownloadPattern method [Print Devices]
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintOemUni3.DownloadPattern
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni3::DownloadPattern method


## -description


The <code>IPrintOemUni3::DownloadPattern</code> method downloads a pattern to a printer.


## -syntax


````
HRESULT DownloadPattern(
   PDEVOBJ pdevobj,
   SURFOBJ *psoPattern,
   LONG    lPatternID
);
````


## -parameters




### -param pdevobj

A pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param psoPattern

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569901">SURFOBJ</a> structure that contains the pattern to download.


### -param lPatternID

The ID of the pattern to download.


## -returns



If successful, this method should return S_OK. Otherwise, this method should return an appropriate value in the returned HRESULT.




## -remarks



This method is available in Windows Vista and later.

You should implement this method if you want your rendering plug-in, rather than Unidrv, to download a pattern. If implemented, this method is called by <b>DrvRealizeBrush</b> for raster-mode print jobs. This method is not called for vector-mode print jobs.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556273">DrvRealizeBrush</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUni3::DownloadPattern method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

