---
UID: NF:prcomoem.IPrintOemDriverUni.DrvWriteAbortBuf
title: IPrintOemDriverUni::DrvWriteAbortBuf (prcomoem.h)
description: The IPrintOemDriverUni::DrvWriteAbortBuf method is provided by the Unidrv driver to allow an OEM rendering plug-in to send printer clean-up code after a user terminates a print job.
old-location: print\iprintoemdriveruni_drvwriteabortbuf.htm
tech.root: print
ms.assetid: 4f7aff9b-32cf-42a0-ba3b-ddc87ecdb8c3
ms.date: 04/20/2018
ms.keywords: DrvWriteAbortBuf, DrvWriteAbortBuf method [Print Devices], DrvWriteAbortBuf method [Print Devices],IPrintOemDriverUni interface, IPrintOemDriverUni interface [Print Devices],DrvWriteAbortBuf method, IPrintOemDriverUni.DrvWriteAbortBuf, IPrintOemDriverUni::DrvWriteAbortBuf, prcomoem/IPrintOemDriverUni::DrvWriteAbortBuf, print.iprintoemdriveruni_drvwriteabortbuf, print_unidrv-pscript_rendering_cadf14c7-6a07-4245-a912-d790f11b9edc.xml
ms.topic: method
f1_keywords:
 - "prcomoem/IPrintOemDriverUni.DrvWriteAbortBuf"
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
- IPrintOemDriverUni.DrvWriteAbortBuf
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemDriverUni::DrvWriteAbortBuf


## -description


The <code>IPrintOemDriverUni::DrvWriteAbortBuf</code> method is provided by the Unidrv driver to allow an OEM <a href="https://docs.microsoft.com/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-in</a> to send printer clean-up code after a user terminates a print job.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param pBuffer

Caller-supplied pointer to a buffer containing a code fragment to be sent to the printer.


### -param cbSize

Caller-supplied number of bytes in the buffer pointed to by <i>pBuffer</i>.


### -param dwWait

Caller-supplied length of time the printer must wait, in milliseconds, before it can start a new print job after the current job is aborted. 


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



OEMs use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf">IPrintOemDriverUni::DrvWriteSpoolBuf</a> to send output to the printer. If a print job is terminated by the user, <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> returns E_FAIL and can no longer be used to send any data to the printer. When this occurs, certain printers must have a clean-up code fragment sent to them, resetting their states before they can start new print jobs. For these printers, <code>IPrintOemDriverUni::DrvWritetAbortBuf</code> is used to send this code fragment to the printer.

<code>IPrintOemDriverUni::DrvWriteAbortBuf</code> can only be called after <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> has returned E_FAIL. <code>IPrintOemDriverUni::DrvWriteAbortBuf</code> should not be called more than once per job. 

Rendering plug-ins are described in <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customizing-microsoft-s-printer-drivers">Customizing Microsoft's Printer Drivers</a>.



