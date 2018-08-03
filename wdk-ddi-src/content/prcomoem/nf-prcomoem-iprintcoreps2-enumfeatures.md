---
UID: NF:prcomoem.IPrintCorePS2.EnumFeatures
title: IPrintCorePS2::EnumFeatures
author: windows-driver-content
description: The IPrintCorePS2::EnumFeatures method enumerates a printer's available features.
old-location: print\iprintcoreps2_enumfeatures.htm
tech.root: print
ms.assetid: 0a8d1b25-da39-4bdc-a7d7-0d472e94e165
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: EnumFeatures, EnumFeatures method [Print Devices], EnumFeatures method [Print Devices],IPrintCorePS2 interface, IPrintCorePS2 interface [Print Devices],EnumFeatures method, IPrintCorePS2.EnumFeatures, IPrintCorePS2::EnumFeatures, prcomoem/IPrintCorePS2::EnumFeatures, print.iprintcoreps2_enumfeatures, print_unidrv-pscript_rendering_18d27b1c-4ccd-4fba-afe4-e50a1b97910b.xml
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
req.lib: 
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
-	IPrintCorePS2.EnumFeatures
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCorePS2::EnumFeatures


## -description


The <code>IPrintCorePS2::EnumFeatures</code> method enumerates a printer's available features.


## -parameters




### -param pdevobj [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a> structure.


### -param dwFlags [in]

Is reserved and must be set to zero.


### -param pmszFeatureList [out]

Pointer to a caller-supplied buffer that receives a null-delimited list of feature keywords in MULTI_SZ format. The list is terminated with two null characters.

Set this parameter to <b>NULL</b> to simply query for the size (*<i>pcbNeeded</i>) of the feature list without having the list filled in.


### -param cbSize [in]

Specifies the size, in bytes, of the buffer pointed to by <i>pmszFeatureList</i>.


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
The <i>pdevobj</i> parameter pointed to an invalid driver context object.

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



<a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">printer-sticky</a> features (see <a href="https://msdn.microsoft.com/b7f79841-f82c-4a60-9c2f-58772a65a5eb">Replacing Driver-Supplied Property Sheet Pages</a>), such as those that determine installable memory and the presence of optional accessories, are included in the feature keyword list, which appears in the output buffer pointed to by <i>pmszFeatureList</i>. For Pscript5, such features have the <b>OpenGroupType</b> feature attribute set to "InstallableOptions". 

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

This method is supported for any Pscript5 render plug-in.

For more information, see <a href="https://msdn.microsoft.com/4a87cedf-066a-445b-ad3e-71699c9d3e07">Using EnumFeatures</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a>



<a href="https://msdn.microsoft.com/bf7e15df-49ba-4850-acf6-dab5dc137f48">IPrintCorePS2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552996">IPrintCorePS2::EnumOptions</a>
 

 

