---
UID: NF:prcomoem.IPrintCoreHelperPS.GetFeatureAttribute
title: IPrintCoreHelperPS::GetFeatureAttribute (prcomoem.h)
description: The IPrintCoreHelperPS::GetFeatureAttribute method retrieves the feature attribute list or the value of a specific feature attribute.
old-location: print\iprintcorehelperps_getfeatureattribute.htm
tech.root: print
ms.assetid: bf5d9081-20c8-43da-a71f-f089c2885b49
ms.date: 04/20/2018
ms.keywords: GetFeatureAttribute, GetFeatureAttribute method [Print Devices], GetFeatureAttribute method [Print Devices],IPrintCoreHelperPS interface, IPrintCoreHelperPS interface [Print Devices],GetFeatureAttribute method, IPrintCoreHelperPS.GetFeatureAttribute, IPrintCoreHelperPS::GetFeatureAttribute, prcomoem/IPrintCoreHelperPS::GetFeatureAttribute, print.iprintcorehelperps_getfeatureattribute, print_unidrv-pscript_allplugins_19fb9a4e-5314-486b-a1cc-0b9c4bcc690a.xml
ms.topic: method
f1_keywords:
 - "prcomoem/IPrintCoreHelperPS.GetFeatureAttribute"
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
- IPrintCoreHelperPS.GetFeatureAttribute
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperPS::GetFeatureAttribute


## -description


The <b>IPrintCoreHelperPS::GetFeatureAttribute</b> method retrieves the feature attribute list or the value of a specific feature attribute.


## -parameters




### -param pszFeatureKeyword [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the feature keyword to query for. This value can be obtained from a prior call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperps-enumfeatures">IPrintCoreHelperPS::EnumFeatures</a>.


### -param pszAttribute [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the attribute that was requested. If this parameter is <b>NULL</b>, the caller is requesting a list of all of the supported feature attribute names instead of specifying a specific feature attribute name. 


### -param pdwDataType [out]

A pointer to a variable that receives a value that specifies the data type of the requested attribute. This value is an enumerator of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ne-printoem-_eattribute_datatype">EATTRIBUTE_DATATYPE</a> enumeration type, which is defined in printoem.h.


### -param ppbData




### -param pcbSize [out]

A pointer to a variable that receives the size, in bytes, of the buffer that is pointed to by the <i>pbData</i> parameter. 


#### - pbData [out]

A pointer to a callee-allocated buffer containing the requested data. Upon completion of this method, the caller does not need to release this buffer.


## -returns



<b>IPrintCoreHelperPS::GetFeatureAttribute</b> should return one of the following values. 

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
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The method failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The method attempted to query for a nonexistent attribute.

This value might also mean that the feature keyword was not recognized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The value in <i>pcbSize</i> was smaller than the number of bytes to be written to the output buffer that is pointed to by <i>pbData</i>.

This value might also mean that the method was called with <i>pbData</i> set to <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



If <b>IPrintCoreHelperPS::GetFeatureAttribute</b> is called with its <i>pszAttribute</i> and <i>pbData</i> parameters set to <b>NULL</b>, the method returns with *<i>pcbSize</i> set to the number of bytes that are needed for the list of all of the supported attribute names for the feature. If this method is called a second time, with <i>pszAttribute</i> set to <b>NULL</b> and <i>pbData</i> pointing to a buffer of the size that was specified in *<i>pcbSize</i> in the previous call, the method returns with *<i>pdwDataType</i> set to kADT_ASCII (an enumerator of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ne-printoem-_eattribute_datatype">EATTRIBUTE_DATATYPE</a> enumeration type) and <i>pbData</i> pointing to a NULL-delimited list of all of the supported attribute names for the feature. This list is terminated with two null characters.

For more information about <b>IPrintCoreHelperPS::GetFeatureAttribute</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/using-getfeatureattribute">Using GetFeatureAttribute</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperps">IPrintCoreHelperPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperps-getglobalattribute">IPrintCoreHelperPS::GetGlobalAttribute</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperps-getoptionattribute">IPrintCoreHelperPS::GetOptionAttribute</a>
 

 

