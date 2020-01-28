---
UID: NF:prcomoem.IPrintCoreUI2.EnumFeatures
title: IPrintCoreUI2::EnumFeatures (prcomoem.h)
description: The IPrintCoreUI2::EnumFeatures method enumerates a printer's available features.
old-location: print\iprintcoreui2_enumfeatures.htm
tech.root: print
ms.assetid: e5c16b6d-555d-4360-b781-4d22be81ab56
ms.date: 04/20/2018
ms.keywords: EnumFeatures, EnumFeatures method [Print Devices], EnumFeatures method [Print Devices],IPrintCoreUI2 interface, IPrintCoreUI2 interface [Print Devices],EnumFeatures method, IPrintCoreUI2.EnumFeatures, IPrintCoreUI2::EnumFeatures, prcomoem/IPrintCoreUI2::EnumFeatures, print.iprintcoreui2_enumfeatures, print_unidrv-pscript_ui_2eb51928-70ab-48f5-a17e-845c54fbd1aa.xml
f1_keywords:
 - "prcomoem/IPrintCoreUI2.EnumFeatures"
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
- IPrintCoreUI2.EnumFeatures
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreUI2::EnumFeatures


## -description


The <code>IPrintCoreUI2::EnumFeatures</code> method enumerates a printer's available features.


## -parameters




### -param poemuiobj [in]

Pointer to the current context, an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a> structure.


### -param dwFlags [in]

Is reserved and must be set to zero.


### -param pmszFeatureList [out]

Pointer to a caller-supplied buffer that receives a null-delimited list of feature keywords in MULTI_SZ format. The list is terminated with two null characters.

Set this parameter to <b>NULL</b> to simply query for the size (*<i>pcbNeeded</i>) of the feature list without having the list filled in.


### -param cbSize [in]

Specifies the size, in bytes, of the buffer pointed to by <i>pmszFeatureList</i>.


### -param pcbNeeded [out]

Pointer to a memory location that receives the actual size, in bytes, of the feature list.


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
The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pmszFeatureList</i>).

The method was called with <i>pmszFeatureList</i> set to <b>NULL</b>.

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



This method is supported only for Windows XP Pscript5 plug-ins, not for Unidrv plug-ins. 

<a href="https://docs.microsoft.com/windows-hardware/drivers/">printer-sticky</a> features (see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/replacing-driver-supplied-property-sheet-pages">Replacing Driver-Supplied Property Sheet Pages</a>), such as those that determine installable memory and the presence of optional accessories, are included in the feature keyword list, which appears in the output buffer pointed to by <i>pmszFeatureList</i> when the method returns. For Pscript5, such features have the <b>OpenGroupType</b> feature attribute set to "InstallableOptions". 

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/using-enumfeatures">Using EnumFeatures</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcoreui2">IPrintCoreUI2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcoreui2-enumoptions">IPrintCoreUI2::EnumOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a>
 

 

