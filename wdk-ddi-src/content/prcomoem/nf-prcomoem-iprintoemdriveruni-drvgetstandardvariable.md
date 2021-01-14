---
UID: NF:prcomoem.IPrintOemDriverUni.DrvGetStandardVariable
title: IPrintOemDriverUni::DrvGetStandardVariable (prcomoem.h)
description: The IPrintOemDriverUni::DrvGetStandardVariable method is provided by the Unidrv driver so that rendering plug-ins can obtain the current value of Unidrv's standard variables.
old-location: print\iprintoemdriveruni_drvgetstandardvariable.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintOemDriverUni::DrvGetStandardVariable"]
ms.keywords: DrvGetStandardVariable, DrvGetStandardVariable method [Print Devices], DrvGetStandardVariable method [Print Devices],IPrintOemDriverUni interface, IPrintOemDriverUni interface [Print Devices],DrvGetStandardVariable method, IPrintOemDriverUni.DrvGetStandardVariable, IPrintOemDriverUni::DrvGetStandardVariable, prcomoem/IPrintOemDriverUni::DrvGetStandardVariable, print.iprintoemdriveruni_drvgetstandardvariable, print_unidrv-pscript_rendering_001f3a93-7022-4436-8191-5cb091bc3c42.xml
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
 - IPrintOemDriverUni::DrvGetStandardVariable
 - prcomoem/IPrintOemDriverUni::DrvGetStandardVariable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemDriverUni::DrvGetStandardVariable
---

# IPrintOemDriverUni::DrvGetStandardVariable


## -description

The <code>IPrintOemDriverUni::DrvGetStandardVariable</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain the current value of Unidrv's <a href="/windows-hardware/drivers/print/standard-variables">standard variables</a>.

## -parameters

### -param pdevobj

Caller-supplied pointer to a <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.

### -param dwIndex

Caller-supplied, SVI_-prefixed index into the list of Unidrv's standard variables. The SVI_-prefixed index values are defined in printoem.h.

### -param pBuffer

Caller-supplied pointer to a DWORD to receive the standard variable's current value.

### -param cbSize

Caller-supplied size of the buffer pointed to by <i>pBuffer</i>.

### -param pcbNeeded

Caller-supplied pointer to a location to receive the minimum buffer size required to contain the requested information.

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

