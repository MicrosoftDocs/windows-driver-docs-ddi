---
UID: NF:prcomoem.IPrintCorePS2.EnumOptions
title: IPrintCorePS2::EnumOptions (prcomoem.h)
description: The IPrintCorePS2::EnumOptions method enumerates the available options of a specific feature.
old-location: print\iprintcoreps2_enumoptions.htm
tech.root: print
ms.assetid: 2a861450-0bc5-432b-bf5d-9a9761c22ea1
ms.date: 04/20/2018
ms.keywords: EnumOptions, EnumOptions method [Print Devices], EnumOptions method [Print Devices],IPrintCorePS2 interface, IPrintCorePS2 interface [Print Devices],EnumOptions method, IPrintCorePS2.EnumOptions, IPrintCorePS2::EnumOptions, prcomoem/IPrintCorePS2::EnumOptions, print.iprintcoreps2_enumoptions, print_unidrv-pscript_rendering_d4f92055-f090-4794-854e-f6d26f482fd7.xml
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
- IPrintCorePS2.EnumOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCorePS2::EnumOptions


## -description


The <code>IPrintCorePS2::EnumOptions</code> method enumerates the available options of a specific feature.


## -parameters




### -param pdevobj [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a> structure.


### -param dwFlags [in]

Is reserved and must be set to zero.


### -param pszFeatureKeyword [in]

Pointer to a caller-supplied buffer containing an ASCII string, specifying a feature keyword whose options are requested.


### -param pmszOptionList [out]

Pointer to a caller-supplied buffer that receives a null-delimited list, in MULTI_SZ format, containing the option keywords for the feature keyword pointed to by <i>pszFeatureKeyword</i>. This list is terminated with two null characters. 

Set this parameter to <b>NULL</b> to simply query for the size (*<i>pcbNeeded</i>) of the option list without having the list filled in.


### -param cbSize [in]

Specifies the size, in bytes, of the buffer pointed to by <i>pmszOptionList</i>.


### -param pcbNeeded [out]

Pointer to a memory location that receives the actual size, in bytes, of the requested data.


## -returns



This method must return one of the following values.

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
The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pmszOptionList</i>).

The method was called with <i>pmszOptionList</i> set to <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The string pointed to by <i>pszFeatureKeyword</i> is not a recognized feature.

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
(Pscript only)

The Pscript5 driver feature is not supported under the current configuration.

The Pscript5 driver feature is supported under the current configuration, but the Pscript5 driver feature's options are not enumerable.

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



To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

This method is supported for any Pscript5 render plug-in.

For more information, see <a href="https://msdn.microsoft.com/6ce16d28-eff7-4701-a592-046f364cda44">Using EnumOptions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a>



<a href="https://msdn.microsoft.com/bf7e15df-49ba-4850-acf6-dab5dc137f48">IPrintCorePS2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552990">IPrintCorePS2::EnumFeatures</a>
 

 

