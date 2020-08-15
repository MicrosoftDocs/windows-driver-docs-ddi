---
UID: NF:wdfregistry.WdfRegistryRemoveKey
title: WdfRegistryRemoveKey function (wdfregistry.h)
description: The WdfRegistryRemoveKey method removes the registry key that is associated with a specified framework registry-key object and then deletes the registry-key object.
old-location: wdf\wdfregistryremovekey.htm
tech.root: wdf
ms.assetid: b23d1c2f-15f0-4b9e-8a10-9b81056fa509
ms.date: 02/26/2018
keywords: ["WdfRegistryRemoveKey function"]
ms.keywords: DFRegKeyObjectRef_448264d5-1720-46e3-b493-b195825db91f.xml, WdfRegistryRemoveKey, WdfRegistryRemoveKey method, kmdf.wdfregistryremovekey, wdf.wdfregistryremovekey, wdfregistry/WdfRegistryRemoveKey
f1_keywords:
 - "wdfregistry/WdfRegistryRemoveKey"
 - "WdfRegistryRemoveKey"
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
- WdfRegistryRemoveKey
targetos: Windows
req.typenames: 
---

# WdfRegistryRemoveKey function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryRemoveKey</b> method removes the registry key that is associated with a specified framework registry-key object and then deletes the registry-key object.


## -parameters




### -param Key 
[in]
A handle to a registry-key object that represents an opened registry key.


## -returns



<b>WdfRegistryRemoveKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryremovekey">WdfRegistryRemoveKey</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver did not open the registry key with deletion access.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
See the Remarks section.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



<div class="alert"><b>Note</b>  <p class="note">From a KMDF driver, do not call <b>WdfRegistryRemoveKey</b> and then <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryclose">WdfRegistryClose</a> on the same key. The WDFKEY is no longer valid after <b>WdfRegistryRemoveKey</b> returns.

</div>
<div> </div>
While it is legal for a UMDF driver to call <b>WdfRegistryRemoveKey</b>, the call always returns <b>STATUS_NOT_IMPLEMENTED</b>.   To delete the WDFKEY object, a UMDF driver should instead call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryclose">WdfRegistryClose</a>.

<b>WdfRegistryRemoveKey</b> does not return STATUS_SUCCESS if the specified key object represents a registry key that has subkeys. In other words, the driver must remove the subkeys first.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example removes a registry key and deletes the registry-key object.

```cpp
NTSTATUS  status;

status = WdfRegistryRemoveKey(Key);
```


