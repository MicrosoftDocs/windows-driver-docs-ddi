---
UID: NF:wdfregistry.WdfRegistryOpenKey
title: WdfRegistryOpenKey function
author: windows-driver-content
description: The WdfRegistryOpenKey method opens a specified registry key and creates a framework registry-key object that represents the registry key.
old-location: wdf\wdfregistryopenkey.htm
old-project: wdf
ms.assetid: a79f6f98-1ebb-498e-9e20-cfdd22a0da7a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRegistryOpenKey
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
req.alt-api: WdfRegistryOpenKey
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
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
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# WdfRegistryOpenKey function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryOpenKey</b> method opens a specified registry key and creates a framework registry-key object that represents the registry key.



## -syntax

````
NTSTATUS WdfRegistryOpenKey(
  _In_opt_ WDFKEY                 ParentKey,
  _In_     PCUNICODE_STRING       KeyName,
  _In_     ACCESS_MASK            DesiredAccess,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES KeyAttributes,
  _Out_    WDFKEY                 *Key
);
````


## -parameters

### -param ParentKey [in, optional]

A handle to a framework registry-key object. This object represents a parent registry key that the driver has opened. This parameter is optional and can be <b>NULL</b>. If the parameter is not <b>NULL</b>, the key that <i>KeyName</i> specifies must reside under this parent key in the registry. For more information about this parent key, see the Remarks section.


### -param KeyName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the name of the key to be opened. The key name can include path information. If <i>ParentKey</i> is <b>NULL</b>, <i>KeyName</i> must specify a complete path to a registry key. For examples, see the Remarks section.


### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>-typed value that specifies access rights that the driver is requesting for the specified registry key. For a list of access rights that drivers typically use for registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558746">Opening a Handle to a Registry-Key Object</a>. Your driver must ask for only the types of access that it needs. For example, the driver must not ask for KEY_ALL_ACCESS if it will only read the registry key. 


### -param KeyAttributes [in, optional]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Key [out]

A pointer to a location that receives a handle to the new registry-key object.


## -returns
<b>WdfRegistryOpenKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
<a href="..\wdfregistry\nf-wdfregistry-wdfregistryopenkey.md">WdfRegistryOpenKey</a> was not called at IRQL = PASSIVE_LEVEL. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was specified.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A registry-key object could not be allocated.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The system denied the specified access rights.
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>The specified registry key does not exist.

 

For a list of other return values that the <b>WdfRegistryOpenKey</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
To obtain a handle to a registry-key object that represents a parent key, your driver can call <a href="..\wdfdriver\nf-wdfdriver-wdfdriveropenparametersregistrykey.md">WdfDriverOpenParametersRegistryKey</a>, <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceopenregistrykey.md">WdfDeviceOpenRegistryKey</a>, or <a href="..\wdffdo\nf-wdffdo-wdffdoinitopenregistrykey.md">WdfFdoInitOpenRegistryKey</a>.

The string format specified in the <i>KeyName</i> parameter  depends on whether the caller is a KMDF driver or a UMDF driver. For example, to open the following path:


<b>HKLM\System\CurrentControlSet\Control</b>



<b>HKLM\System\CurrentControlSet\Control</b>

Your driver might use this conditional logic:

When the driver has finished using a registry key that it opens with <b>WdfRegistryOpenKey</b>, the driver must call <a href="..\wdfregistry\nf-wdfregistry-wdfregistryclose.md">WdfRegistryClose</a>.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.

The following code example opens a driver's software key, and then it opens the <b>MySubKey</b> registry key, which is located under the driver's software key.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceopenregistrykey.md">WdfDeviceOpenRegistryKey</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdfdriveropenparametersregistrykey.md">WdfDriverOpenParametersRegistryKey</a>
</dt>
<dt>
<a href="..\wdffdo\nf-wdffdo-wdffdoinitopenregistrykey.md">WdfFdoInitOpenRegistryKey</a>
</dt>
<dt>
<a href="..\wdfregistry\nf-wdfregistry-wdfregistryclose.md">WdfRegistryClose</a>
</dt>
<dt>
<a href="..\wdfregistry\nf-wdfregistry-wdfregistrycreatekey.md">WdfRegistryCreateKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryOpenKey method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

