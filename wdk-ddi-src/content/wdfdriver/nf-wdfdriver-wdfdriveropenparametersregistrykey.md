---
UID: NF:wdfdriver.WdfDriverOpenParametersRegistryKey
title: WdfDriverOpenParametersRegistryKey function
author: windows-driver-content
description: The WdfDriverOpenParametersRegistryKey method opens the driver's Parameters registry key and retrieves a handle to a framework registry-key object that represents the key.
old-location: wdf\wdfdriveropenparametersregistrykey.htm
old-project: wdf
ms.assetid: e0f22096-3d82-4e1c-9398-d5e441fbb473
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDriverObjectRef_c79992f7-2a85-4c1b-859d-9bfdf441a9c4.xml, WdfDriverOpenParametersRegistryKey, WdfDriverOpenParametersRegistryKey method, kmdf.wdfdriveropenparametersregistrykey, wdf.wdfdriveropenparametersregistrykey, wdfdriver/WdfDriverOpenParametersRegistryKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	WdfDriverOpenParametersRegistryKey
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_INIT_FLAGS
req.product: Windows 10 or later.
---

# WdfDriverOpenParametersRegistryKey function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDriverOpenParametersRegistryKey</b> method opens the driver's <b>Parameters</b> registry key and retrieves a handle to a framework registry-key object that represents the key.


## -syntax


````
NTSTATUS WdfDriverOpenParametersRegistryKey(
  _In_     WDFDRIVER              Driver,
  _In_     ACCESS_MASK            DesiredAccess,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES KeyAttributes,
  _Out_    WDFKEY                 *Key
);
````


## -parameters




### -param Driver [in]

A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> or <a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>.


### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>-typed value that specifies an access mask for the <b>Parameters</b> registry key.

A KMDF driver typically requests <b>KEY_READ</b>, <b>KEY_WRITE</b>, or <b>KEY_READ | KEY_WRITE</b>.

If you are writing a UMDF driver, use <b>KEY_READ</b> or <b>KEY_READ | KEY_SET_VALUE</b>.

As a best practice, ask for only the types of access that your driver needs.


### -param KeyAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the framework registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Key [out]

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


Because the above values are invalid for UMDF drivers, universal flags such as GENERIC_ALL and STANDARD_RIGHTS_ALL also cause <a href="..\wdfdriver\nf-wdfdriver-wdfdriveropenparametersregistrykey.md">WdfDriverOpenParametersRegistryKey</a> to fail with this return value.

</td>
</tr>
</table>
 

For more information about return values, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A system bug check occurs if a KMDF driver specifies an invalid handle in <i>Driver</i>.




## -remarks



The driver's <b>Parameters</b> key is located in the registry's <a href="https://msdn.microsoft.com/library/windows/hardware/dn926947">Services</a> tree. If the driver's <b>Parameters</b> key does not exist, the <b>WdfDriverOpenParametersRegistryKey</b> method creates it. 

When the driver has finished using the <b>Parameters</b> registry key, the driver must call <a href="..\wdfregistry\nf-wdfregistry-wdfregistryclose.md">WdfRegistryClose</a>.

For more information about the registry, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example opens a driver's <b>Parameters</b> registry key and obtains a handle to a framework registry-key object that represents the key.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFKEY hKey;

status = WdfDriverOpenParametersRegistryKey(
                                            Driver,
                                            STANDARD_RIGHTS_ALL,
                                            WDF_NO_OBJECT_ATTRIBUTES,
                                            &amp;hKey
                                            );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryclose.md">WdfRegistryClose</a>



<a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>



<a href="..\wdfdriver\nf-wdfdriver-wdfdrivergetregistrypath.md">WdfDriverGetRegistryPath</a>



<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>



<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDriverOpenParametersRegistryKey method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

