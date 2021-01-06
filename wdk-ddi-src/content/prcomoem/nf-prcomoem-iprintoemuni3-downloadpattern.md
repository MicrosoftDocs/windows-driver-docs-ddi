---
UID: NF:prcomoem.IPrintOemUni3.DownloadPattern
title: IPrintOemUni3::DownloadPattern (prcomoem.h)
description: The IPrintOemUni3::DownloadPattern method downloads a pattern to a printer.
old-location: print\iprintoemuni3_downloadpattern.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintOemUni3::DownloadPattern"]
ms.keywords: DownloadPattern, DownloadPattern method [Print Devices], DownloadPattern method [Print Devices],IPrintOemUni3 interface, IPrintOemUni3 interface [Print Devices],DownloadPattern method, IPrintOemUni3.DownloadPattern, IPrintOemUni3::DownloadPattern, prcomoem/IPrintOemUni3::DownloadPattern, print.iprintoemuni3_downloadpattern, print_unidrv-pscript_rendering_ce79f65e-3515-4d0b-96d6-d468c15039f1.xml
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
 - IPrintOemUni3::DownloadPattern
 - prcomoem/IPrintOemUni3::DownloadPattern
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemUni3.DownloadPattern
---

# IPrintOemUni3::DownloadPattern


## -description

The <code>IPrintOemUni3::DownloadPattern</code> method downloads a pattern to a printer.

## -parameters

### -param pdevobj

A pointer to a <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.

### -param psoPattern

A pointer to the <a href="/windows/win32/api/winddi/ns-winddi-surfobj">SURFOBJ</a> structure that contains the pattern to download.

### -param lPatternID

The ID of the pattern to download.

## -returns

If successful, this method should return S_OK. Otherwise, this method should return an appropriate value in the returned HRESULT.

## -remarks

This method is available in Windows Vista and later.

You should implement this method if you want your rendering plug-in, rather than Unidrv, to download a pattern. If implemented, this method is called by <b>DrvRealizeBrush</b> for raster-mode print jobs. This method is not called for vector-mode print jobs.

## -see-also

<a href="/windows/win32/api/winddi/nf-winddi-drvrealizebrush">DrvRealizeBrush</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemuni3">IPrintOemUni3</a>
