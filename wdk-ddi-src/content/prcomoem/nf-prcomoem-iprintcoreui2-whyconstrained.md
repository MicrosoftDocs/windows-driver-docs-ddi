---
UID: NF:prcomoem.IPrintCoreUI2.WhyConstrained
title: IPrintCoreUI2::WhyConstrained (prcomoem.h)
description: The IPrintCoreUI2::WhyConstrained method determines why the specified feature/option selection is constrained.
old-location: print\iprintcoreui2_whyconstrained.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintCoreUI2::WhyConstrained"]
ms.keywords: IPrintCoreUI2 interface [Print Devices],WhyConstrained method, IPrintCoreUI2.WhyConstrained, IPrintCoreUI2::WhyConstrained, WhyConstrained, WhyConstrained method [Print Devices], WhyConstrained method [Print Devices],IPrintCoreUI2 interface, prcomoem/IPrintCoreUI2::WhyConstrained, print.iprintcoreui2_whyconstrained, print_unidrv-pscript_ui_4ab02889-5bb1-412e-8bc3-2b0f5bb63088.xml
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
 - IPrintCoreUI2::WhyConstrained
 - prcomoem/IPrintCoreUI2::WhyConstrained
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintCoreUI2.WhyConstrained
---

# IPrintCoreUI2::WhyConstrained


## -description

The <code>IPrintCoreUI2::WhyConstrained</code> method determines why the specified feature/option selection is constrained.

## -parameters

### -param poemuiobj 

[in]
Pointer to the current context, an <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a> structure.

### -param dwFlags 

[in]
Is reserved and must be set to zero.

### -param pszFeatureKeyword 

[in]
Pointer to a caller-supplied buffer containing the single feature keyword of interest to the caller.

### -param pszOptionKeyword 

[in]
Pointer to a caller-supplied buffer containing the option keyword.

### -param pmszReasonList 

[out]
Pointer to a caller-supplied buffer that receives a list of the feature/option keyword pairs that place constraints on the specified feature/option. This list is in MULTI_SZ format with each item in the list separated from the next by a null character. The list is terminated with two null characters.

Set this parameter to <b>NULL</b> to simply query for the size (*<i>pcbNeeded</i>) of the reason list without having the list filled in.

### -param cbSize 

[in]
Specifies the size, in bytes, of the buffer pointed to by <i>pmszReasonList</i>.

### -param pcbNeeded 

[out]
Pointer to a memory location that receives the actual size, in bytes, of the reason list.

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
The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pmszReasonList</i>).

The method was called with <i>pmszReasonList</i> set to <b>NULL</b>.

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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The <i>poemuiobj</i> parameter pointed to an invalid context object.

The feature keyword or option keyword was not recognized.

The feature stickiness (see <a href="/windows-hardware/drivers/print/replacing-driver-supplied-property-sheet-pages">Replacing Driver-Supplied Property Sheet Pages</a>) did not match that specified in the current context.

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

When a user of the OEM UI attempts to select an item that is constrained, the caller can use this method to display a message explaining why the item is constrained. When this method returns, <i>pmszReasonList</i> points to a list of one or more feature/option pairs that appear in the current driver settings, but conflict with the selected feature/option keywords. If there were no conflicts, the method should return S_OK, <i>pmszReasonList</i> should be filled in with an empty ASCII string containing only a null character, and *<i>pcbNeeded</i> should be set to 1.

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

## -see-also

<a href="/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcoreui2">IPrintCoreUI2</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcoreui2-enumconstrainedoptions">IPrintCoreUI2::EnumConstrainedOptions</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">IPrintOemUI::DevicePropertySheets</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a>



<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a>
