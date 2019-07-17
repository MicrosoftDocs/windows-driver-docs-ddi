---
UID: NF:wdfregistry.WdfRegistryQueryString
title: WdfRegistryQueryString function (wdfregistry.h)
description: The WdfRegistryQueryString method retrieves the string data that is currently assigned to a specified registry string value and assigns the string to a specified framework string object.
old-location: wdf\wdfregistryquerystring.htm
tech.root: wdf
ms.assetid: 2c1242ea-5d77-464e-9203-ef2236ea4619
ms.date: 02/26/2018
ms.keywords: DFRegKeyObjectRef_d3260d42-afdc-4858-a0b4-e2ae90327066.xml, WdfRegistryQueryString, WdfRegistryQueryString method, kmdf.wdfregistryquerystring, wdf.wdfregistryquerystring, wdfregistry/WdfRegistryQueryString
ms.topic: function
f1_keywords:
 - "wdfregistry/WdfRegistryQueryString"
req.header: wdfregistry.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfRegistryQueryString
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRegistryQueryString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryQueryString</b> method retrieves the string data that is currently assigned to a specified registry string value and assigns the string to a specified framework string object.


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a name for the registry value. 


### -param String [in]

A handle to a framework string object. The framework will assign the registry value's string data to this object.


## -returns



<b>WdfRegistryQueryString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryquerystring">WdfRegistryQueryString</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to complete the operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver did not open the registry key with KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS access.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The data type of the registry value that the <i>ValueName</i> parameter specified was not REG_SZ.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The registry value was not available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RESOURCE_DATA_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The registry value exists under the specified key, but is empty. 

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfRegistryQueryString</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.



This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



To obtain a string from a string object, your driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfstring/nf-wdfstring-wdfstringgetunicodestring">WdfStringGetUnicodeString</a>. 

For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example creates a string object, retrieves string data from a registry key, and obtains the string data from the string object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UNICODE_STRING str;
WDFSTRING string;
NTSTATUS status;
DECLARE_CONST_UNICODE_STRING(valueName, STRING_VALUE_NAME);

status = WdfStringCreate(
                         NULL,
                         WDF_NO_OBJECT_ATTRIBUTES,
                         &string
                         );
if (NT_SUCCESS(status)) {
    status = WdfRegistryQueryString(
                                    Key, 
                                    &valueName,
                                    string
                                    );
    if (NT_SUCCESS(status)) {
        WdfStringGetUnicodeString(
                                  string,
                                  &str
                                  );
    }
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryquerymemory">WdfRegistryQueryMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryquerymultistring">WdfRegistryQueryMultiString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryqueryulong">WdfRegistryQueryULong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryqueryunicodestring">WdfRegistryQueryUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryqueryvalue">WdfRegistryQueryValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfstring/nf-wdfstring-wdfstringcreate">WdfStringCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfstring/nf-wdfstring-wdfstringgetunicodestring">WdfStringGetUnicodeString</a>
 

 

