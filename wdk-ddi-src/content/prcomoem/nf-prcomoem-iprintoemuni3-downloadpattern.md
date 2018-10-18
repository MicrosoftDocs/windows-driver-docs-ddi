---
UID: NF:prcomoem.IPrintOemUni3.DownloadPattern
title: IPrintOemUni3::DownloadPattern
author: windows-driver-content
description: The IPrintOemUni3::DownloadPattern method downloads a pattern to a printer.
old-location: print\iprintoemuni3_downloadpattern.htm
tech.root: print
ms.assetid: 7604a6df-c73a-4114-916f-1e777a323731
ms.date: 4/20/2018
ms.keywords: DownloadPattern, DownloadPattern method [Print Devices], DownloadPattern method [Print Devices],IPrintOemUni3 interface, IPrintOemUni3 interface [Print Devices],DownloadPattern method, IPrintOemUni3.DownloadPattern, IPrintOemUni3::DownloadPattern, prcomoem/IPrintOemUni3::DownloadPattern, print.iprintoemuni3_downloadpattern, print_unidrv-pscript_rendering_ce79f65e-3515-4d0b-96d6-d468c15039f1.xml
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
-	IPrintOemUni3.DownloadPattern
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni3::DownloadPattern


## -description


The <code>IPrintOemUni3::DownloadPattern</code> method downloads a pattern to a printer.


## -parameters




### -param pdevobj

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a> structure.


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



<a href="https://msdn.microsoft.com/cf5705fb-8420-4eec-99d4-d56f192da581">IPrintOemUni3</a>
 

 

