---
UID: NF:wdfregistry.WdfRegistryCreateKey
title: WdfRegistryCreateKey function (wdfregistry.h)
description: The WdfRegistryCreateKey method creates and opens a specified registry key, or just opens the key if it already exists, and creates a framework registry-key object that represents the registry key.
old-location: wdf\wdfregistrycreatekey.htm
tech.root: wdf
ms.assetid: acaf7024-b73a-4fe5-89e2-83e28cf2fdd1
ms.date: 02/26/2018
keywords: ["WdfRegistryCreateKey function"]
ms.keywords: DFRegKeyObjectRef_400650ea-7915-45f5-bcdd-2de1a02041f0.xml, WdfRegistryCreateKey, WdfRegistryCreateKey method, kmdf.wdfregistrycreatekey, wdf.wdfregistrycreatekey, wdfregistry/WdfRegistryCreateKey
f1_keywords:
 - "wdfregistry/WdfRegistryCreateKey"
 - "WdfRegistryCreateKey"
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
- WdfRegistryCreateKey
targetos: Windows
req.typenames: 
---

# WdfRegistryCreateKey function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryCreateKey</b> method creates and opens a specified registry key, or just opens the key if it already exists, and creates a framework registry-key object that represents the registry key.


## -parameters




### -param ParentKey 
[in, optional]
A handle to a framework registry-key object. This object represents a parent registry key that the driver has opened. This parameter is optional and can be <b>NULL</b>. If the parameter is not <b>NULL</b>, the key that <i>KeyName</i> specifies must reside under this parent key in the registry. For more information about this parent key, see the Remarks section.


### -param KeyName 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the name of the key to be opened. The key name can include path information. If <i>ParentKey</i> is <b>NULL</b>, <i>KeyName</i> must specify a complete path to a registry key.


### -param DesiredAccess 
[in]
An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>-typed value that specifies access rights that the driver is requesting for the specified registry key. For a list of access rights that drivers typically use for registry keys, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/opening-a-handle-to-a-registry-key-object">Opening a Handle to a Registry-Key Object</a>. Your driver must ask for only the types of access that it needs. For example, the driver must not ask for KEY_ALL_ACCESS if it will only read the registry key. 


### -param CreateOptions 
[in]
One or more flags. For information about these flags, see the <i>CreateOptions</i> parameter or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>.


### -param CreateDisposition 
[out, optional]
A pointer to a location that receives REG_CREATED_NEW_KEY if a new key is created or REG_OPENED_EXISTING_KEY if an existing key is opened. These values are defined in <i>Wdm.h</i>. This pointer is optional and can be <b>NULL</b>.


### -param KeyAttributes 
[in, optional]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Key 
[out]
A pointer to a location that receives a handle to the new registry-key object.


## -returns



<b>WdfRegistryCreateKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistrycreatekey">WdfRegistryCreateKey</a> was not called at IRQL = PASSIVE_LEVEL. 

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
 

For a list of other return values that the <b>WdfRegistryCreateKey</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.



This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



To obtain a handle to a registry-key object that represents a parent key, your driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdriveropenparametersregistrykey">WdfDriverOpenParametersRegistryKey</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceopenregistrykey">WdfDeviceOpenRegistryKey</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitopenregistrykey">WdfFdoInitOpenRegistryKey</a>.

By default, the new registry-key object's parent is the framework driver object that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a> method creates. You can use the <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the registry-key object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the registry-key object when it has finished using the object; otherwise, the registry-key object will remain until the I/O manager unloads your driver. 

 If your driver does not change the default parent, the driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryclose">WdfRegistryClose</a> when it has finished using the object; otherwise, the registry-key object will remain until the I/O manager unloads your driver. Alternatively,  the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a> to delete the registry-key object.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example opens a driver's software key, and then it creates and opens the <b>MySubKey</b> registry key, which is located under the driver's software key.

```cpp
WDFKEY  hKey, subkey;
NTSTATUS  status;
UNICODE_STRING  myKeyStr;

status = WdfDeviceOpenRegistryKey(
                                  device,
                                  PLUGPLAY_REGKEY_DRIVER,
                                  KEY_READ,
                                  WDF_NO_OBJECT_ATTRIBUTES,
                                  &hKey
                                  );
if (NT_SUCCESS(status)){
    RtlInitUnicodeString(
                         &mySubKey,
                         L"MySubKey"
                         );
    status = WdfRegistryCreateKey(
                                  hKey,
                                  &myKeyStr,
                                  KEY_READ,
                                  REG_OPTION_NON_VOLATILE,
                                  NULL,
                                  WDF_NO_OBJECT_ATTRIBUTES,
                                  &subkey
                                  );
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring">RtlInitUnicodeString</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceopenregistrykey">WdfDeviceOpenRegistryKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdriveropenparametersregistrykey">WdfDriverOpenParametersRegistryKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitopenregistrykey">WdfFdoInitOpenRegistryKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryopenkey">WdfRegistryOpenKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>
 

 

