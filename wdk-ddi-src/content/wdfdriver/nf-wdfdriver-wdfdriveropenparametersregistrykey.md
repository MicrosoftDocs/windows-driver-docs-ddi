---
UID: NF:wdfdriver.WdfDriverOpenParametersRegistryKey
title: WdfDriverOpenParametersRegistryKey function (wdfdriver.h)
description: The WdfDriverOpenParametersRegistryKey method opens the driver's Parameters registry key and retrieves a handle to a framework registry-key object that represents the key.
old-location: wdf\wdfdriveropenparametersregistrykey.htm
tech.root: wdf
ms.assetid: e0f22096-3d82-4e1c-9398-d5e441fbb473
ms.date: 02/26/2018
keywords: ["WdfDriverOpenParametersRegistryKey function"]
ms.keywords: DFDriverObjectRef_c79992f7-2a85-4c1b-859d-9bfdf441a9c4.xml, WdfDriverOpenParametersRegistryKey, WdfDriverOpenParametersRegistryKey method, kmdf.wdfdriveropenparametersregistrykey, wdf.wdfdriveropenparametersregistrykey, wdfdriver/WdfDriverOpenParametersRegistryKey
req.header: wdfdriver.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDriverOpenParametersRegistryKey
 - wdfdriver/WdfDriverOpenParametersRegistryKey
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
 - WdfDriverOpenParametersRegistryKey
---

# WdfDriverOpenParametersRegistryKey function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDriverOpenParametersRegistryKey</b> method opens the driver's <b>Parameters</b> registry key and retrieves a handle to a framework registry-key object that represents the key.

## -parameters

### -param Driver 

[in]
A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfgetdriver">WdfGetDriver</a>.

### -param DesiredAccess 

[in]
An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>-typed value that specifies an access mask for the <b>Parameters</b> registry key.

A KMDF driver typically requests <b>KEY_READ</b>, <b>KEY_WRITE</b>, or <b>KEY_READ | KEY_WRITE</b>.

If you are writing a UMDF driver, use <b>KEY_READ</b> or <b>KEY_READ | KEY_SET_VALUE</b>.

As a best practice, ask for only the types of access that your driver needs.

### -param KeyAttributes 

[in, optional]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the framework registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param Key 

[out]
A pointer to a location that receives a handle to a framework registry-key object.

## -returns

<b>WdfDriverOpenParametersRegistryKey</b> returns STATUS_SUCCESS if the operation succeeds. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
 A UMDF driver specified one of the following flags in the <i>DesiredAccess</i> parameter:<ul>
<li>GENERIC_WRITE</li>
<li>KEY_CREATE_SUBKEY</li>
<li>WRITE_DAC</li>
</ul>


Because the above values are invalid for UMDF drivers, universal flags such as GENERIC_ALL and STANDARD_RIGHTS_ALL also cause <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdriveropenparametersregistrykey">WdfDriverOpenParametersRegistryKey</a> to fail with this return value.

</td>
</tr>
</table>
 

For more information about return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A system bug check occurs if a KMDF driver specifies an invalid handle in <i>Driver</i>.

## -remarks

The driver's <b>Parameters</b> key is located in the registry's <a href="https://docs.microsoft.com/windows-hardware/test/wpt/services">Services</a> tree. If the driver's <b>Parameters</b> key does not exist, the <b>WdfDriverOpenParametersRegistryKey</b> method creates it. 

When the driver has finished using the <b>Parameters</b> registry key, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryclose">WdfRegistryClose</a>.

For more information about the registry, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example opens a driver's <b>Parameters</b> registry key and obtains a handle to a framework registry-key object that represents the key.

```cpp
WDFKEY hKey;

status = WdfDriverOpenParametersRegistryKey(
                                            Driver,
                                            STANDARD_RIGHTS_ALL,
                                            WDF_NO_OBJECT_ATTRIBUTES,
                                            &hKey
                                            );
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivergetregistrypath">WdfDriverGetRegistryPath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfgetdriver">WdfGetDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryclose">WdfRegistryClose</a>

