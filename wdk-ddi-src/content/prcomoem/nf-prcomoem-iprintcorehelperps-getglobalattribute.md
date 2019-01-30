---
UID: NF:prcomoem.IPrintCoreHelperPS.GetGlobalAttribute
title: IPrintCoreHelperPS::GetGlobalAttribute (prcomoem.h)
description: The IPrintCoreHelperPS::GetGlobalAttribute method retrieves the global attribute list or the value of a specific global attribute.
old-location: print\iprintcorehelperps_getglobalattribute.htm
tech.root: print
ms.assetid: 4243ac31-83a7-47b5-8406-9d9537fbeb11
ms.date: 04/20/2018
ms.keywords: GetGlobalAttribute, GetGlobalAttribute method [Print Devices], GetGlobalAttribute method [Print Devices],IPrintCoreHelperPS interface, IPrintCoreHelperPS interface [Print Devices],GetGlobalAttribute method, IPrintCoreHelperPS.GetGlobalAttribute, IPrintCoreHelperPS::GetGlobalAttribute, prcomoem/IPrintCoreHelperPS::GetGlobalAttribute, print.iprintcorehelperps_getglobalattribute, print_unidrv-pscript_allplugins_9c11e4ae-21bd-493c-b4d0-39b8406c8843.xml
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
-	IPrintCoreHelperPS.GetGlobalAttribute
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperPS::GetGlobalAttribute


## -description


The <b>IPrintCoreHelperPS::GetGlobalAttribute</b> method retrieves the global attribute list or the value of a specific global attribute.


## -parameters




### -param pszAttribute [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the requested attribute. If this parameter is <b>NULL</b>, the caller is requesting a list of all of the supported global attribute names instead of specifying a specific global attribute name. 


### -param pdwDataType [out]

A pointer to variable that receives a value that specifies the data type of the requested attribute. This value is an enumerator of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548692">EATTRIBUTE_DATATYPE</a> enumeration type, which is defined in printoem.h. 


### -param ppbData




### -param pcbSize [out]

A pointer to a variable that specifies the size, in bytes, of the buffer that is pointed to by the <i>pbData</i> parameter. 


#### - pbData [out]

A pointer to a callee-allocated buffer containing the requested data. Upon completion of this method, the caller does not need to release this buffer.


## -returns



<b>IPrintCoreHelperPS::GetGlobalAttribute</b> should return one of the following values.

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



If <b>IPrintCoreHelperPS::GetGlobalAttribute</b> is called with its <i>pszAttribute</i> and <i>pbData</i> parameters set to <b>NULL</b>, the method returns with *<i>pcbSize</i> set to the number of bytes that are needed for the list of all of the supported global attribute names. If this method is called a second time, with <i>pszAttribute</i> set to <b>NULL</b> and <i>pbData</i> pointing to a buffer of the size that was specified in *<i>pcbSize</i> in the previous call, the method returns with *<i>pdwDataType</i> set to kADT_ASCII (an enumerator of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548692">EATTRIBUTE_DATATYPE</a> enumeration type) and <i>pbData</i> pointing to a NULL-delimited list of all of the supported global attribute names. This list is terminated with two null characters.

For more information about <b>IPrintCoreHelperPS::GetGlobalAttribute</b>, see <a href="https://msdn.microsoft.com/0e23ecba-7d89-44f5-b6a7-7d6be9a56765">Using GetGlobalAttribute</a>. 




## -see-also




<a href="https://msdn.microsoft.com/2be594f1-1eb1-42e0-a345-ee7edf4d96dd">IPrintCoreHelperPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551998">IPrintCoreHelperPS::GetFeatureAttribute</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552903">IPrintCoreHelperPS::GetOptionAttribute</a>
 

 

