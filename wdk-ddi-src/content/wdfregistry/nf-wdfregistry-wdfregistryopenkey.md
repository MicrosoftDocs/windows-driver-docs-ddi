---
UID: NF:wdfregistry.WdfRegistryOpenKey
title: WdfRegistryOpenKey function (wdfregistry.h)
description: The WdfRegistryOpenKey method opens a specified registry key and creates a framework registry-key object that represents the registry key.
old-location: wdf\wdfregistryopenkey.htm
tech.root: wdf
ms.assetid: a79f6f98-1ebb-498e-9e20-cfdd22a0da7a
ms.date: 02/26/2018
ms.keywords: DFRegKeyObjectRef_a53062c9-844d-4a0f-bfea-738b0adba93c.xml, WdfRegistryOpenKey, WdfRegistryOpenKey method, kmdf.wdfregistryopenkey, wdf.wdfregistryopenkey, wdfregistry/WdfRegistryOpenKey
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
- WdfRegistryOpenKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRegistryOpenKey function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryOpenKey</b> method opens a specified registry key and creates a framework registry-key object that represents the registry key.


## -parameters




### -param ParentKey [in, optional]

A handle to a framework registry-key object. This object represents a parent registry key that the driver has opened. This parameter is optional and can be <b>NULL</b>. If the parameter is not <b>NULL</b>, the key that <i>KeyName</i> specifies must reside under this parent key in the registry. For more information about this parent key, see the Remarks section.


### -param KeyName [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the name of the key to be opened. The key name can include path information. If <i>ParentKey</i> is <b>NULL</b>, <i>KeyName</i> must specify a complete path to a registry key. For examples, see the Remarks section.


### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>-typed value that specifies access rights that the driver is requesting for the specified registry key. For a list of access rights that drivers typically use for registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558746">Opening a Handle to a Registry-Key Object</a>. Your driver must ask for only the types of access that it needs. For example, the driver must not ask for KEY_ALL_ACCESS if it will only read the registry key. 


### -param KeyAttributes [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Key [out]

A pointer to a location that receives a handle to the new registry-key object.


## -returns



<b>WdfRegistryOpenKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549919">WdfRegistryOpenKey</a> was not called at IRQL = PASSIVE_LEVEL. 

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
A registry-key object could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The system denied the specified access rights.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The specified registry key does not exist.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfRegistryOpenKey</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



To obtain a handle to a registry-key object that represents a parent key, your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547202">WdfDriverOpenParametersRegistryKey</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff546804">WdfDeviceOpenRegistryKey</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547249">WdfFdoInitOpenRegistryKey</a>.

The string format specified in the <i>KeyName</i> parameter  depends on whether the caller is a KMDF driver or a UMDF driver. For example, to open the following path:


<b>HKLM\System\CurrentControlSet\Control</b>



Your driver might use this conditional logic:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#ifdef _KERNEL_MODE
#define CONTROL_KEY_FULL_PATH L"\\Registry\\Machine\\System\\CurrentControlSet\\Control "
#else
#define CONTROL_KEY_FULL_PATH L"System\\CurrentControlSet\\Control\\" 
#endif
</pre>
</td>
</tr>
</table></span></div>
When the driver has finished using a registry key that it opens with <b>WdfRegistryOpenKey</b>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549914">WdfRegistryClose</a>.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example opens a driver's software key, and then it opens the <b>MySubKey</b> registry key, which is located under the driver's software key.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFKEY  hKey, subkey;
NTSTATUS  status;
UNICODE_STRING myKeyStr;

status = WdfDeviceOpenRegistryKey(
                                  device,
                                  PLUGPLAY_REGKEY_DRIVER,
                                  KEY_READ,
                                  WDF_NO_OBJECT_ATTRIBUTES,
                                  &hKey
                                  );
if (NT_SUCCESS(status)){
    RtlInitUnicodeString(
                         &myKeyStr,
                         L"MySubKey"
                         );
    status = WdfRegistryOpenKey(
                                hKey,
                                &myKeyStr,
                                KEY_READ,
                                WDF_NO_OBJECT_ATTRIBUTES,
                                &subkey
                                );
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546804">WdfDeviceOpenRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547202">WdfDriverOpenParametersRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547249">WdfFdoInitOpenRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549914">WdfRegistryClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549917">WdfRegistryCreateKey</a>
 

 

