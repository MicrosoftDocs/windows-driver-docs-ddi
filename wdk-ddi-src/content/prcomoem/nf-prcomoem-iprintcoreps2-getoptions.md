---
UID: NF:prcomoem.IPrintCorePS2.GetOptions
title: IPrintCorePS2::GetOptions (prcomoem.h)
description: The IPrintCorePS2::GetOptions method retrieves the driver's current feature settings in the format of a list of feature/option keyword pairs.
old-location: print\iprintcoreps2_getoptions.htm
tech.root: print
ms.assetid: 8f5df76b-57c9-4c5a-9ca2-f02c8d903a8b
ms.date: 04/20/2018
keywords: ["IPrintCorePS2::GetOptions"]
ms.keywords: GetOptions, GetOptions method [Print Devices], GetOptions method [Print Devices],IPrintCorePS2 interface, IPrintCorePS2 interface [Print Devices],GetOptions method, IPrintCorePS2.GetOptions, IPrintCorePS2::GetOptions, prcomoem/IPrintCorePS2::GetOptions, print.iprintcoreps2_getoptions, print_unidrv-pscript_rendering_5efb04dd-f01b-4da4-9ac3-34a3e62a1ec3.xml
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
 - IPrintCorePS2::GetOptions
 - prcomoem/IPrintCorePS2::GetOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintCorePS2.GetOptions
---

# IPrintCorePS2::GetOptions


## -description

The <code>IPrintCorePS2::GetOptions</code> method retrieves the driver's current feature settings in the format of a list of feature/option keyword pairs.

## -parameters

### -param pdevobj 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.

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
Pointer to a caller-supplied buffer that receives a list of feature/option keyword pairs (in MULTI_SZ format) obtained from the driver settings. Each feature/option keyword pair contains the feature keyword name, a null character, the option keyword name, and another null character. The list is terminated by two NULL characters.

### -param cbSize 

[in]
Specifies the size, in bytes, of the buffer pointed to by <i>pmszFeatureOptionBuf</i>.

### -param pcbNeeded 

[out]
Pointer to a memory location that receives the actual size, in bytes, of the requested data.

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

The <i>pdevobj</i> parameter pointed to an invalid driver context object.

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
The method failed.

</td>
</tr>
</table>

## -remarks

This method supports both <a href="/windows-hardware/drivers/">document-sticky</a> and <a href="/windows-hardware/drivers/">printer-sticky</a> features. It is supported only after the core driver finishes its <a href="/windows/win32/api/winddi/nf-winddi-drvenablepdev">DrvEnablePDEV</a> processing, which sets up all option settings. A call to <code>IPrintCorePS2::GetOptions</code> when it is not supported should cause it to return E_NOTIMPL. For example, when the core driver calls a render plug-in's <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-enablepdev">IPrintOemPS::EnablePDEV</a> method, the driver is still occupied with its <b>DrvEnablePDEV</b> processing, so if the plug-in calls <code>IPrintCorePS2::GetOptions</code> within the plug-in's <b>IPrintOemPS::DevMode</b> method, the plug-in receives the E_NOTIMPL return value. However, because the plug-in's <b>IPrintOemPS::EnablePDEV</b> method is called after the core driver finishes its <b>DrvEnablePDEV</b> processing, the plug-in is able to call <code>IPrintCorePS2::GetOptions</code> successfully within its <b>IPrintOemPS::EnablePDEV</b> method.

If a requested feature keyword is not recognized, or the feature is recognized but there is currently no option selection for it, the feature is ignored and the feature/option keyword pair is not placed in the output buffer.

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

This method is supported for any Pscript5 render plug-in.

For more information, see <a href="/windows-hardware/drivers/print/using-getoptions-and-setoptions">Using GetOptions and SetOptions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a>



<a href="/windows/win32/api/winddi/nf-winddi-drvenablepdev">DrvEnablePDEV</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcoreps2">IPrintCorePS2</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-devmode">IPrintOemPS::DevMode</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-enablepdev">IPrintOemPS::EnablePDEV</a>