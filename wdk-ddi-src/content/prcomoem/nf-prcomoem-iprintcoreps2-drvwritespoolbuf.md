---
UID: NF:prcomoem.IPrintCorePS2.DrvWriteSpoolBuf
title: IPrintCorePS2::DrvWriteSpoolBuf (prcomoem.h)
description: The IPrintCorePS2::DrvWriteSpoolBuf method is provided by the Pscript5 driver so that a rendering plug-in can send printer data to the spooler.
old-location: print\iprintcoreps2_drvwritespoolbuf.htm
tech.root: print
ms.assetid: 25405dd8-730e-4de6-af44-9dd584ed3087
ms.date: 04/20/2018
ms.keywords: DrvWriteSpoolBuf, DrvWriteSpoolBuf method [Print Devices], DrvWriteSpoolBuf method [Print Devices],IPrintCorePS2 interface, IPrintCorePS2 interface [Print Devices],DrvWriteSpoolBuf method, IPrintCorePS2.DrvWriteSpoolBuf, IPrintCorePS2::DrvWriteSpoolBuf, prcomoem/IPrintCorePS2::DrvWriteSpoolBuf, print.iprintcoreps2_drvwritespoolbuf, print_unidrv-pscript_rendering_56d81faa-5b82-4d07-beb1-9a8a82fc7409.xml
f1_keywords:
 - "prcomoem/IPrintCorePS2.DrvWriteSpoolBuf"
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
- IPrintCorePS2.DrvWriteSpoolBuf
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCorePS2::DrvWriteSpoolBuf


## -description


The <code>IPrintCorePS2::DrvWriteSpoolBuf</code> method is provided by the Pscript5 driver so that a <a href="https://docs.microsoft.com/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-in</a> can send printer data to the spooler.


## -parameters




### -param pdevobj [in]

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param pBuffer [in]

Caller-supplied pointer to a buffer containing data to be sent to the print spooler.


### -param cbSize [in]

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



This method has the same behavior as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverps-drvwritespoolbuf">IPrintOemDriverPS::DrvWriteSpoolBuf</a>. This method is supported for any Pscript5 render plug-ins.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcoreps2">IPrintCorePS2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverps-drvwritespoolbuf">IPrintOemDriverPS::DrvWriteSpoolBuf</a>
 

 

