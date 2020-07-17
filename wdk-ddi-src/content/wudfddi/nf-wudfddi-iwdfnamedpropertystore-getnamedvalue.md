---
UID: NF:wudfddi.IWDFNamedPropertyStore.GetNamedValue
title: IWDFNamedPropertyStore::GetNamedValue (wudfddi.h)
description: The GetNamedValue method retrieves the value of a property.
old-location: wdf\iwdfnamedpropertystore_getnamedvalue.htm
tech.root: wdf
ms.assetid: 9581e3af-f7f8-4365-8bb2-daedcb7a3280
ms.date: 02/26/2018
keywords: ["IWDFNamedPropertyStore::GetNamedValue"]
ms.keywords: GetNamedValue, GetNamedValue method, GetNamedValue method,IWDFNamedPropertyStore interface, IWDFNamedPropertyStore interface,GetNamedValue method, IWDFNamedPropertyStore.GetNamedValue, IWDFNamedPropertyStore::GetNamedValue, UMDFPropertyStoreObjectRef_ba3dd45a-7045-4798-81c6-35cb1a743cc4.xml, umdf.iwdfnamedpropertystore_getnamedvalue, wdf.iwdfnamedpropertystore_getnamedvalue, wudfddi/IWDFNamedPropertyStore::GetNamedValue
f1_keywords:
 - "wudfddi/IWDFNamedPropertyStore.GetNamedValue"
 - "IWDFNamedPropertyStore.GetNamedValue"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFNamedPropertyStore.GetNamedValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFNamedPropertyStore::GetNamedValue


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNamedValue</b> method retrieves the value of a property.


## -parameters




### -param pszName [in]

A pointer to a null-terminated string that contains the name of the property.


### -param pv [out]

A pointer to a variable that receives the value for the property. 


## -returns



<b>GetNamedValue</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



The <b>GetNamedValue</b> method allocates memory for a string in the <a href="https://docs.microsoft.com/windows/desktop/api/propidl/ns-propidl-tagpropvariant">PROPVARIANT</a> structure pointed to by the <i>pv</i> parameter.   The caller must then free this memory by calling the <a href="https://docs.microsoft.com/windows/desktop/api/propidl/nf-propidl-propvariantclear">PropVariantClear</a> function, as shown in the following snippet:

<pre class="syntax" xml:space="preserve"><code>hr = pPropStore->GetNamedValue(L"Host", &val);
...
PropVariantClear(&val);</code></pre>
If the caller does not free the memory, a memory leak may result.

The following variant types are supported for property values. The following table shows the variant type that is returned regardless of the original variant type.

<table>
<tr>
<th>Variant type</th>
<th>Variant type retrieved</th>
</tr>
<tr>
<td>
VT_BSTR

</td>
<td rowspan="3">
While clients read a string value, the value is returned as VT_LPWSTR regardless of the original variant type that was used to write the value.

</td>
</tr>
<tr>
<td>
VT_LPWSTR

</td>
</tr>
<tr>
<td>
VT_LPSTR

</td>
</tr>
<tr>
<td>
VT_I1

</td>
<td rowspan="7">
While clients read an integer value, the value is returned as VT_UI4 regardless of the original variant type that was used to write the value.

</td>
</tr>
<tr>
<td>
VT_UI1

</td>
</tr>
<tr>
<td>
VT_I2

</td>
</tr>
<tr>
<td>
VT_UI2

</td>
</tr>
<tr>
<td>
VT_I4

</td>
</tr>
<tr>
<td>
VT_UI4

</td>
</tr>
<tr>
<td>
VT_UINT

</td>
</tr>
<tr>
<td>
VT_BLOB

</td>
<td>
The binary value is returned as VT_BLOB.

</td>
</tr>
<tr>
<td>
VT_VECTOR | VT_LPWSTR

</td>
<td>
The string array is returned as VT_VECTOR | VT_LPWSTR

</td>
</tr>
</table>
 

A string that contains environment variables is expanded on read.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfnamedpropertystore">IWDFNamedPropertyStore</a>



<a href="https://docs.microsoft.com/windows/desktop/api/propidl/ns-propidl-tagpropvariant">PROPVARIANT</a>



<a href="https://docs.microsoft.com/windows/desktop/api/propidl/nf-propidl-propvariantclear">PropVariantClear</a>
 

 

