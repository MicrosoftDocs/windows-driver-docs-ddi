---
UID: NF:prcomoem.IPrintOemDriverPS.DrvWriteSpoolBuf
title: IPrintOemDriverPS::DrvWriteSpoolBuf (prcomoem.h)
description: The IPrintOemDriverPS::DrvWriteSpoolBuf method is provided by the Pscript5 driver so that rendering plug-ins can send printer data to the spooler.
old-location: print\iprintoemdriverps_drvwritespoolbuf.htm
tech.root: print
ms.assetid: 91eb36b3-ea05-4a5e-8bba-47c262a4fa4a
ms.date: 04/20/2018
keywords: ["IPrintOemDriverPS::DrvWriteSpoolBuf"]
ms.keywords: DrvWriteSpoolBuf, DrvWriteSpoolBuf method [Print Devices], DrvWriteSpoolBuf method [Print Devices],IPrintOemDriverPS interface, IPrintOemDriverPS interface [Print Devices],DrvWriteSpoolBuf method, IPrintOemDriverPS.DrvWriteSpoolBuf, IPrintOemDriverPS::DrvWriteSpoolBuf, prcomoem/IPrintOemDriverPS::DrvWriteSpoolBuf, print.iprintoemdriverps_drvwritespoolbuf, print_unidrv-pscript_rendering_aa71a302-dc97-4bc2-8cbb-fd32c6237e74.xml
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
 - IPrintOemDriverPS::DrvWriteSpoolBuf
 - prcomoem/IPrintOemDriverPS::DrvWriteSpoolBuf
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemDriverPS.DrvWriteSpoolBuf
---

# IPrintOemDriverPS::DrvWriteSpoolBuf


## -description

The <code>IPrintOemDriverPS::DrvWriteSpoolBuf</code> method is provided by the Pscript5 driver so that <a href="/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-ins</a> can send printer data to the spooler.

## -parameters

### -param pdevobj

Caller-supplied pointer to a <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.

### -param pBuffer

Caller-supplied pointer to a buffer containing data to be sent to the print spooler.

### -param cbSize

Caller-supplied value representing the size, in bytes, of the buffer pointed to by <i>pBuffer</i>.

### -param pdwResult 

[out]
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
The operation failed

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

Rendering plug-ins are described in <a href="/windows-hardware/drivers/print/customizing-microsoft-s-printer-drivers">Customizing Microsoft's Printer Drivers</a>.