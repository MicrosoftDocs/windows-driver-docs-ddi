---
UID: NF:prcomoem.IPrintOemDriverUni.DrvGetGPDData
title: IPrintOemDriverUni::DrvGetGPDData (prcomoem.h)
description: The IPrintOemDriverUni::DrvGetGPDData method is provided by the Unidrv driver so that rendering plug-ins can obtain data defined in a printer's GPD file.
old-location: print\iprintoemdriveruni_drvgetgpddata.htm
tech.root: print
ms.assetid: cebe8972-4e5a-4382-ac1b-4c326dea46b1
ms.date: 04/20/2018
keywords: ["IPrintOemDriverUni::DrvGetGPDData"]
ms.keywords: DrvGetGPDData, DrvGetGPDData method [Print Devices], DrvGetGPDData method [Print Devices],IPrintOemDriverUni interface, IPrintOemDriverUni interface [Print Devices],DrvGetGPDData method, IPrintOemDriverUni.DrvGetGPDData, IPrintOemDriverUni::DrvGetGPDData, prcomoem/IPrintOemDriverUni::DrvGetGPDData, print.iprintoemdriveruni_drvgetgpddata, print_unidrv-pscript_rendering_3efd30f6-350c-411f-a036-f6fe3525132d.xml
f1_keywords:
 - "prcomoem/IPrintOemDriverUni.DrvGetGPDData"
 - "IPrintOemDriverUni.DrvGetGPDData"
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
- IPrintOemDriverUni.DrvGetGPDData
targetos: Windows
req.typenames: 
---

# IPrintOemDriverUni::DrvGetGPDData


## -description


The <code>IPrintOemDriverUni::DrvGetGPDData</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain data defined in a printer's <a href="https://docs.microsoft.com/windows-hardware/drivers/">GPD</a> file.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param dwType

Caller-supplied flag indicating the type of GPD data being requested. Currently, the following flag is the only one defined:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
GPD_OEMCUSTOMDATA

</td>
<td>
The method returns the string associated with a GPD file's *<b>OEMCustomData</b> entry.

</td>
</tr>
</table>
 


### -param pInputData

Reserved. Must be zero.


### -param pBuffer

Caller-supplied pointer to a buffer to receive the requested information.


### -param cbSize

Caller-supplied size, in bytes, of the buffer pointed to by <i>pBuffer</i>.


### -param pcbNeeded

Receives the driver-supplied minimum buffer size, in bytes, required to contain the requested information.


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



If the buffer specified by <i>pBuffer</i> and <i>cbSize</i> is too small to receive the requested information, Unidrv supplies the required buffer size in the location pointed to by <i>pcbNeeded</i>, returns E_FAIL, and sets the error code to ERROR_INSUFFICIENT_BUFFER.



