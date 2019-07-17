---
UID: NF:prcomoem.IPrintOemDriverUni.DrvWriteSpoolBuf
title: IPrintOemDriverUni::DrvWriteSpoolBuf (prcomoem.h)
description: The IPrintOemDriverUni::DrvWriteSpoolBuf method is provided by the Unidrv driver so that a rendering plug-in can send printer data to the spooler.
old-location: print\iprintoemdriveruni_drvwritespoolbuf.htm
tech.root: print
ms.assetid: e019b88a-bffe-44d2-8031-de37b6a1cf1c
ms.date: 04/20/2018
ms.keywords: DrvWriteSpoolBuf, DrvWriteSpoolBuf method [Print Devices], DrvWriteSpoolBuf method [Print Devices],IPrintOemDriverUni interface, IPrintOemDriverUni interface [Print Devices],DrvWriteSpoolBuf method, IPrintOemDriverUni.DrvWriteSpoolBuf, IPrintOemDriverUni::DrvWriteSpoolBuf, prcomoem/IPrintOemDriverUni::DrvWriteSpoolBuf, print.iprintoemdriveruni_drvwritespoolbuf, print_unidrv-pscript_rendering_ba569121-3277-447a-a53b-3de6e06fd182.xml
ms.topic: method
f1_keywords:
 - "prcomoem/IPrintOemDriverUni.DrvWriteSpoolBuf"
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
- prcomoem.h
api_name:
- IPrintOemDriverUni.DrvWriteSpoolBuf
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemDriverUni::DrvWriteSpoolBuf


## -description


The <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> method is provided by the Unidrv driver so that a <a href="https://docs.microsoft.com/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-in</a> can send printer data to the spooler.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param pBuffer

Caller-supplied pointer to a buffer containing data to be sent to the print spooler.


### -param cbSize

Caller-supplied value representing the size, in bytes, of the buffer pointed to by <i>pBuffer</i>.


### -param pdwResult [out]

Receives a method-supplied value representing the number of bytes sent to the spooler.


## -returns



The method must return one of the following values.

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
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>
 




## -remarks



OEMs use the Unidrv helper function <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> to send output to the printer. If a print job is terminated by the user, <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> returns E_FAIL and can no longer be used to send any data to the printer. When this occurs, certain printers must have a clean-up code fragment sent to them, resetting their states before they can start new print jobs. For these printers, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwriteabortbuf">IPrintOemDriverUni::DrvWriteAbortBuf</a> can be used to send this code fragment to the printer. 

Rendering plug-ins are described in <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customizing-microsoft-s-printer-drivers">Customizing Microsoft's Printer Drivers</a>.



