---
UID: NF:prcomoem.IPrintCoreUI2.GetOptions
title: IPrintCoreUI2::GetOptions (prcomoem.h)
description: The IPrintCoreUI2::GetOptions method retrieves the driver's current feature settings in the format of a list of feature/option keyword pairs.
old-location: print\iprintcoreui2_getoptions.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintCoreUI2::GetOptions"]
ms.keywords: GetOptions, GetOptions method [Print Devices], GetOptions method [Print Devices],IPrintCoreUI2 interface, IPrintCoreUI2 interface [Print Devices],GetOptions method, IPrintCoreUI2.GetOptions, IPrintCoreUI2::GetOptions, prcomoem/IPrintCoreUI2::GetOptions, print.iprintcoreui2_getoptions, print_unidrv-pscript_ui_9d2ad553-1fd3-4420-9b30-c73a41c28c8d.xml
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
 - IPrintCoreUI2::GetOptions
 - prcomoem/IPrintCoreUI2::GetOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintCoreUI2::GetOptions
---

# IPrintCoreUI2::GetOptions


## -description

The <code>IPrintCoreUI2::GetOptions</code> method retrieves the driver's current feature settings in the format of a list of feature/option keyword pairs.

## -parameters

### -param poemuiobj 

[in]
Pointer to the current context, an <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a> structure.

### -param dwFlags 

[in]
Is reserved and must be set to zero.

### -param pmszFeaturesRequested 

[in]
Pointer to caller-supplied buffer containing a list of feature keywords (in MULTI_SZ format) whose settings are requested. Set this parameter to <b>NULL</b> to obtain settings for all features.

### -param cbIn 

[in]
Specifies the size, in bytes, of the buffer pointed to by <i>pmszFeaturesRequested</i>. The size includes the last MULTI_SZ null character.

### -param pmszFeatureOptionBuf 

[out]
Pointer to a caller-supplied buffer that receives a list of feature/option keyword pairs (in MULTI_SZ format) obtained from the driver settings. Each feature/option keyword pair contains the feature keyword name, a null character, the option keyword name, and another null character. The list is terminated by two null characters.

### -param cbSize 

[in]
Specifies the size, in bytes, of the buffer pointed to by <i>pmszFeatureOptionBuf</i>.

### -param pcbNeeded 

[out]
Pointer to a memory location that receives the actual size, in bytes, of the feature/option keyword pairs.

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
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pmszFeatureOptionBuf</i>).

The method was called with <i>pmszFeatureOptionBuf</i> set to <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The input buffer (the buffer pointed to by <i>pmszFeaturesRequested</i>) was provided, but its contents were not in MULTI_SZ format.

The <i>poemuiobj</i> parameter pointed to an invalid context object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The method failed

</td>
</tr>
</table>

## -remarks

This method is supported only for Windows XP Pscript5 UI plug-ins that fully replace the core driver's standard UI pages, and is supported only during the UI plug-in's <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a> and <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">IPrintOemUI::DevicePropertySheets</a> functions, and their property sheet callback routines. See <a href="/windows-hardware/drivers/print/replacing-driver-supplied-property-sheet-pages">Replacing Driver-Supplied Property Sheet Pages</a> for more information.

If a requested feature keyword is not recognized, or recognized but not supported in the current sticky mode (<a href="/windows-hardware/drivers/">document-sticky</a> or <a href="/windows-hardware/drivers/">printer-sticky</a> -- see <a href="/windows-hardware/drivers/print/replacing-driver-supplied-property-sheet-pages">Replacing Driver-Supplied Property Sheet Pages</a>), or the feature keyword is recognized but there is currently no option selection for it, the feature is simply ignored and the feature/option keyword pair is not placed in the output buffer.

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

For more information, see <a href="/windows-hardware/drivers/print/using-getoptions-and-setoptions">Using GetOptions and SetOptions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcoreui2">IPrintCoreUI2</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcoreui2-setoptions">IPrintCoreUI2::SetOptions</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">IPrintOemUI::DevicePropertySheets</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a>



<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a>

