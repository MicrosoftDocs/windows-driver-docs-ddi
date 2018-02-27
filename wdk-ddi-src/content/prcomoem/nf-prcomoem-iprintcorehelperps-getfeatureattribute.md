---
UID: NF:prcomoem.IPrintCoreHelperPS.GetFeatureAttribute
title: IPrintCoreHelperPS::GetFeatureAttribute method
author: windows-driver-content
description: The IPrintCoreHelperPS::GetFeatureAttribute method retrieves the feature attribute list or the value of a specific feature attribute.
old-location: print\iprintcorehelperps_getfeatureattribute.htm
old-project: print
ms.assetid: bf5d9081-20c8-43da-a71f-f089c2885b49
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetFeatureAttribute method [Print Devices], GetFeatureAttribute method [Print Devices], IPrintCoreHelperPS interface, GetFeatureAttribute,IPrintCoreHelperPS.GetFeatureAttribute, IPrintCoreHelperPS, IPrintCoreHelperPS interface [Print Devices], GetFeatureAttribute method, IPrintCoreHelperPS::GetFeatureAttribute, prcomoem/IPrintCoreHelperPS::GetFeatureAttribute, print.iprintcorehelperps_getfeatureattribute, print_unidrv-pscript_allplugins_19fb9a4e-5314-486b-a1cc-0b9c4bcc690a.xml
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
-	IPrintCoreHelperPS.GetFeatureAttribute
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelperPS::GetFeatureAttribute method


## -description


The <b>IPrintCoreHelperPS::GetFeatureAttribute</b> method retrieves the feature attribute list or the value of a specific feature attribute.


## -syntax


````
HRESULT GetFeatureAttribute(
  [in]  PCSTR  pszFeatureKeyword,
  [in]  PCSTR  pszAttribute,
  [out] PDWORD pdwDataType,
  [out] PBYTE  *pbData,
  [out] PDWORD pcbSize
);
````


## -parameters




### -param pszFeatureKeyword [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the feature keyword to query for. This value can be obtained from a prior call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551977">IPrintCoreHelperPS::EnumFeatures</a>.


### -param pszAttribute [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the attribute that was requested. If this parameter is <b>NULL</b>, the caller is requesting a list of all of the supported feature attribute names instead of specifying a specific feature attribute name. 


### -param pdwDataType [out]

A pointer to a variable that receives a value that specifies the data type of the requested attribute. This value is an enumerator of the <a href="..\printoem\ne-printoem-_eattribute_datatype.md">EATTRIBUTE_DATATYPE</a> enumeration type, which is defined in printoem.h.


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



If <b>IPrintCoreHelperPS::GetFeatureAttribute</b> is called with its <i>pszAttribute</i> and <i>pbData</i> parameters set to <b>NULL</b>, the method returns with *<i>pcbSize</i> set to the number of bytes that are needed for the list of all of the supported attribute names for the feature. If this method is called a second time, with <i>pszAttribute</i> set to <b>NULL</b> and <i>pbData</i> pointing to a buffer of the size that was specified in *<i>pcbSize</i> in the previous call, the method returns with *<i>pdwDataType</i> set to kADT_ASCII (an enumerator of the <a href="..\printoem\ne-printoem-_eattribute_datatype.md">EATTRIBUTE_DATATYPE</a> enumeration type) and <i>pbData</i> pointing to a NULL-delimited list of all of the supported attribute names for the feature. This list is terminated with two null characters.

For more information about <b>IPrintCoreHelperPS::GetFeatureAttribute</b>, see <a href="https://msdn.microsoft.com/e5050cb1-c178-405d-bb0e-fd7827198bca">Using GetFeatureAttribute</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552903">IPrintCoreHelperPS::GetOptionAttribute</a>



<a href="..\prcomoem\nn-prcomoem-iprintcorehelperps.md">IPrintCoreHelperPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552899">IPrintCoreHelperPS::GetGlobalAttribute</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperPS::GetFeatureAttribute method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

