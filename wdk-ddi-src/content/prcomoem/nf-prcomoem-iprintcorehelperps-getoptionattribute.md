---
UID: NF:prcomoem.IPrintCoreHelperPS.GetOptionAttribute
title: IPrintCoreHelperPS::GetOptionAttribute method
author: windows-driver-content
description: The IPrintCoreHelperPS::GetOptionAttribute method retrieves the option attribute list or the value of a specific option attribute.
old-location: print\iprintcorehelperps_getoptionattribute.htm
old-project: print
ms.assetid: 66e794e6-ded0-41b1-b52b-d886bb58a4ff
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetOptionAttribute method [Print Devices], GetOptionAttribute method [Print Devices], IPrintCoreHelperPS interface, GetOptionAttribute,IPrintCoreHelperPS.GetOptionAttribute, IPrintCoreHelperPS, IPrintCoreHelperPS interface [Print Devices], GetOptionAttribute method, IPrintCoreHelperPS::GetOptionAttribute, prcomoem/IPrintCoreHelperPS::GetOptionAttribute, print.iprintcorehelperps_getoptionattribute, print_unidrv-pscript_allplugins_9c895bf8-2a17-4a3a-b97d-e747f5996318.xml
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
-	IPrintCoreHelperPS.GetOptionAttribute
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelperPS::GetOptionAttribute method


## -description


The <b>IPrintCoreHelperPS::GetOptionAttribute</b> method retrieves the option attribute list or the value of a specific option attribute.


## -syntax


````
HRESULT GetOptionAttribute(
  [in]  PCSTR  pszFeatureKeyword,
  [in]  PCSTR  pszOptionKeyword,
  [in]  PCSTR  pszAttribute,
  [out] PDWORD pdwDataType,
  [out] PBYTE  *pbData,
  [out] PDWORD pcbSize
);
````


## -parameters




### -param pszFeatureKeyword [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the feature keyword to query for. 


### -param pszOptionKeyword [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the option keyword to query for. This value can be obtained from a prior call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551987">IPrintCoreHelperPS::EnumOptions</a>.


### -param pszAttribute [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the attribute requested. If this parameter is <b>NULL</b>, the caller is requesting a list of all supported attribute names for the option instead of specifying a specific attribute name for the option.


### -param pdwDataType [out]

A pointer to a variable that receives a value that specifies the data type of the requested attribute. This value is an enumerator of the <a href="..\printoem\ne-printoem-_eattribute_datatype.md">EATTRIBUTE_DATATYPE</a> enumeration type, which is defined in printoem.h.


### -param ppbData




### -param pcbSize [out]

A pointer to a variable that receives the size, in bytes, of the buffer that is pointed to by the <i>pbData</i> parameter.


#### - pbData [out]

A pointer to a callee-allocated buffer containing the requested data. Upon completion of this method, the caller does not need to release this buffer.


## -returns



<b>IPrintCoreHelperPS::GetOptionAttribute</b> should return one of the following values.

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

This value might also mean that the feature keyword name or option keyword name were not recognized.

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

</td>
</tr>
</table>
 




## -remarks



If <b>IPrintCoreHelperPS::GetOptionAttribute </b>is called with its <i>pszAttribute</i> and <i>pbData</i> parameters set to <b>NULL</b>, the method returns with *<i>pcbSize</i> set to the number of bytes that are needed for the list of all of the supported attribute names for the option. If this method is called a second time, with <i>pszAttribute</i> set to <b>NULL</b> and <i>pbData</i> pointing to a buffer of the size that was specified in *<i>pcbSize</i> in the previous call, the method returns with *<i>pdwDataType</i> set to kADT_ASCII (an enumerator of the <a href="..\printoem\ne-printoem-_eattribute_datatype.md">EATTRIBUTE_DATATYPE</a> enumeration type) and <i>pbData</i> pointing to a NULL-delimited list of all of the supported attribute names for the option. This list is terminated with two null characters.

For more information about <b>IPrintCoreHelperPS::GetOptionAttribute</b>, see <a href="https://msdn.microsoft.com/d35f0811-d572-422c-8672-ffd29bf69efa">Using GetOptionAttribute</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552899">IPrintCoreHelperPS::GetGlobalAttribute</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551998">IPrintCoreHelperPS::GetFeatureAttribute</a>



<a href="..\prcomoem\nn-prcomoem-iprintcorehelperps.md">IPrintCoreHelperPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperPS::GetOptionAttribute method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

