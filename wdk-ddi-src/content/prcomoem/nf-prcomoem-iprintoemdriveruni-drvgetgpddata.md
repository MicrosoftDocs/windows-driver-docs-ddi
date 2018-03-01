---
UID: NF:prcomoem.IPrintOemDriverUni.DrvGetGPDData
title: IPrintOemDriverUni::DrvGetGPDData method
author: windows-driver-content
description: The IPrintOemDriverUni::DrvGetGPDData method is provided by the Unidrv driver so that rendering plug-ins can obtain data defined in a printer's GPD file.
old-location: print\iprintoemdriveruni_drvgetgpddata.htm
old-project: print
ms.assetid: cebe8972-4e5a-4382-ac1b-4c326dea46b1
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DrvGetGPDData method [Print Devices], DrvGetGPDData method [Print Devices], IPrintOemDriverUni interface, DrvGetGPDData,IPrintOemDriverUni.DrvGetGPDData, IPrintOemDriverUni, IPrintOemDriverUni interface [Print Devices], DrvGetGPDData method, IPrintOemDriverUni::DrvGetGPDData, prcomoem/IPrintOemDriverUni::DrvGetGPDData, print.iprintoemdriveruni_drvgetgpddata, print_unidrv-pscript_rendering_3efd30f6-350c-411f-a036-f6fe3525132d.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemDriverUni.DrvGetGPDData
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemDriverUni::DrvGetGPDData method


## -description


The <code>IPrintOemDriverUni::DrvGetGPDData</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain data defined in a printer's <a href="https://msdn.microsoft.com/f67c673d-c6f0-49f0-850a-d8b00e99ddd4">GPD</a> file.


## -syntax


````
HRESULT DrvGetGPDData(
   PDEVOBJ pdevobj,
   DWORD   dwType,
   PVOID   pInputData,
   PVOID   pBuffer,
   DWORD   cbSize,
   PDWORD  pcbNeeded
);
````


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


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



