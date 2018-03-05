---
UID: NF:wdfregistry.WdfRegistryQueryUnicodeString
title: WdfRegistryQueryUnicodeString function
author: windows-driver-content
description: The WdfRegistryQueryUnicodeString method retrieves the string data that is currently assigned to a specified registry string value and copies the string to a specified UNICODE_STRING structure.
old-location: wdf\wdfregistryqueryunicodestring.htm
old-project: wdf
ms.assetid: efbe5526-274b-416b-8e5c-8b18fe754b43
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRegKeyObjectRef_3301cdb3-8fe5-4094-8fc2-717467802680.xml, WdfRegistryQueryUnicodeString, WdfRegistryQueryUnicodeString method, kmdf.wdfregistryqueryunicodestring, wdf.wdfregistryqueryunicodestring, wdfregistry/WdfRegistryQueryUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfRegistryQueryUnicodeString
product: Windows
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# WdfRegistryQueryUnicodeString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryQueryUnicodeString</b> method retrieves the string data that is currently assigned to a specified registry string value and copies the string to a specified <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure.


## -syntax


````
NTSTATUS WdfRegistryQueryUnicodeString(
  _In_      WDFKEY           Key,
  _In_      PCUNICODE_STRING ValueName,
  _Out_opt_ PUSHORT          ValueByteLength,
  _Inout_   PUNICODE_STRING  Value
);
````


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a name for the registry value. 


### -param ValueByteLength [out, optional]

A pointer to a location that receives the number of bytes that are contained in the Unicode string that <i>Value</i> points to, including the terminating <b>NULL</b> byte. This pointer is optional and can be <b>NULL</b>


### -param Value [in, out]

A pointer to a UNICODE_STRING structure that receives the data string for the key that <i>Key</i> specifies. If this parameter is <b>NULL</b> and <i>ValueByteLength</i> is non-<b>NULL</b>, <b>WdfRegistryQueryUnicodeString</b> returns only the size of the string.


## -returns



<b>WdfRegistryQueryUnicodeString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryunicodestring.md">WdfRegistryQueryUnicodeString</a> was not called at IRQL = PASSIVE_LEVEL. 

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
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the <i>Value</i> parameter points to was too small, and only partial data was written to the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the <i>Value</i> parameter points to was too small, and no data was written to the buffer.

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
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example, which is from the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">Serial</a> sample driver, retrieves the Unicode string that represents the string data that is assigned to the <b>PortName</b> value under a device's hardware key.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
SerialReadSymName(
    IN WDFDEVICE Device,
    __out PWCHAR RegName,
    IN OUT PUSHORT LengthOfRegName // In characters
    )
{
    NTSTATUS status;
    WDFKEY hKey;
    UNICODE_STRING value;
    UNICODE_STRING valueName;
    USHORT requiredLength;

    value.Buffer = RegName;
    value.MaximumLength = *LengthOfRegName;
    value.Length = 0;

    status = WdfDeviceOpenRegistryKey(
                                      Device,
                                      PLUGPLAY_REGKEY_DEVICE,
                                      STANDARD_RIGHTS_ALL,
                                      WDF_NO_OBJECT_ATTRIBUTES,
                                      &amp;hKey
                                      );

    if (NT_SUCCESS (status)) {
        RtlInitUnicodeString(
                             &amp;valueName,
                             L"PortName"
                             );
        status = WdfRegistryQueryUnicodeString (
                                      hKey,
                                      &amp;valueName,
                                      &amp;requiredLength,
                                      &amp;value
                                      );
        WdfRegistryClose(hKey);
    }
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryulong.md">WdfRegistryQueryULong</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryqueryvalue.md">WdfRegistryQueryValue</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerymultistring.md">WdfRegistryQueryMultiString</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerystring.md">WdfRegistryQueryString</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryclose.md">WdfRegistryClose</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryquerymemory.md">WdfRegistryQueryMemory</a>



<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryQueryUnicodeString method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

