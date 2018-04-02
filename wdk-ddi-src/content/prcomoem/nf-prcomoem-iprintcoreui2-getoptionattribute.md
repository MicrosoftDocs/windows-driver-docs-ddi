---
UID: NF:prcomoem.IPrintCoreUI2.GetOptionAttribute
title: IPrintCoreUI2::GetOptionAttribute method
author: windows-driver-content
description: The IPrintCoreUI2::GetOptionAttribute method retrieves the option attribute list or the value of a specific option attribute.
old-location: print\iprintcoreui2_getoptionattribute.htm
old-project: print
ms.assetid: cf5420fb-3414-47a7-a53d-3d109589b64d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetOptionAttribute method [Print Devices], GetOptionAttribute method [Print Devices], IPrintCoreUI2 interface, GetOptionAttribute,IPrintCoreUI2.GetOptionAttribute, IPrintCoreUI2, IPrintCoreUI2 interface [Print Devices], GetOptionAttribute method, IPrintCoreUI2::GetOptionAttribute, prcomoem/IPrintCoreUI2::GetOptionAttribute, print.iprintcoreui2_getoptionattribute, print_unidrv-pscript_ui_a6147f0f-da6c-4d71-9d7f-04f3490935f0.xml
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
-	IPrintCoreUI2.GetOptionAttribute
product:
- Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreUI2::GetOptionAttribute method


## -description


The <code>IPrintCoreUI2::GetOptionAttribute</code> method retrieves the option attribute list or the value of a specific option attribute.


## -parameters




### -param poemuiobj [in]

Pointer to the current context, an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559571">OEMUIOBJ</a> structure.


### -param dwFlags [in]

Is reserved and must be set to zero.


### -param pszFeatureKeyword [in]

Pointer to a caller-supplied buffer containing an ASCII string specifying the single feature keyword to query for. 


### -param pszOptionKeyword [in]

Pointer to a caller-supplied buffer containing an ASCII string specifying the single option keyword to query for. This value can be obtained from a prior call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff553052">IPrintCoreUI2::EnumOptions</a>. 


### -param pszAttribute [in]

Pointer to a caller-supplied buffer containing an ASCII string specifying the single attribute requested. If this parameter is <b>NULL</b>, the caller is requesting a list of all supported attribute names for the option, as opposed to specifying a specific attribute name for the option.


### -param pdwDataType [out]

Pointer to a memory location that receives a value specifying the data type of the requested attribute. This value is an enumerator of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548692">EATTRIBUTE_DATATYPE</a> enumeration.


### -param pbData [out]

Pointer to a caller-supplied buffer that receives the requested data. To simply query for the number of bytes needed to fulfill a request, set this parameter to <b>NULL</b>.


### -param cbSize [in]

Specifies the size, in bytes of the buffer pointed to by <i>pbData</i>.


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
The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pbData</i>).

The method was called with <i>pbData</i> set to <b>NULL</b>.

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

The feature keyword name or option keyword name were not recognized.

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

If this method is called with its <i>pszAttribute</i> and <i>pbData</i> parameters set to <b>NULL</b>, the method returns with *<i>pcbNeeded</i> set to the number of bytes needed for the list of all supported attribute names for the option. If the method is called a second time, with <i>pszAttribute</i> set to <b>NULL</b> and <i>pbData</i> pointing to a buffer of the size specified in *<i>pcbNeeded</i> in the previous call, the method returns with *<i>pdwDataType</i> set to kADT_ASCII (an enumerator of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548692">EATTRIBUTE_DATATYPE</a> enumerated type) and <i>pbData</i> pointing to a null-delimited list of all supported attribute names for the option. This list is terminated with two null characters.

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

For more information, see <a href="https://msdn.microsoft.com/d35f0811-d572-422c-8672-ffd29bf69efa">Using GetOptionAttribute</a>.




## -see-also




<a href="https://msdn.microsoft.com/e2d2e486-d69d-4a6d-aaab-a7b8806665b4">IPrintCoreUI2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553052">IPrintCoreUI2::EnumOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553056">IPrintCoreUI2::GetFeatureAttribute</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553059">IPrintCoreUI2::GetGlobalAttribute</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559571">OEMUIOBJ</a>
 

 

