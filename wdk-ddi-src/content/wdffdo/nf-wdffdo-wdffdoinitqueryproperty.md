---
UID: NF:wdffdo.WdfFdoInitQueryProperty
title: WdfFdoInitQueryProperty function
author: windows-driver-content
description: The WdfFdoInitQueryProperty method retrieves a specified device property.
old-location: wdf\wdffdoinitqueryproperty.htm
old-project: wdf
ms.assetid: e58def50-3e35-43d9-9f7e-31283256b204
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectFdoPdoRef_92306389-1cdf-4751-a0c5-552cdb5e4556.xml, WdfFdoInitQueryProperty, WdfFdoInitQueryProperty method, kmdf.wdffdoinitqueryproperty, wdf.wdffdoinitqueryproperty, wdffdo/WdfFdoInitQueryProperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
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
-	WdfFdoInitQueryProperty
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# WdfFdoInitQueryProperty function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfFdoInitQueryProperty</b> method retrieves a specified device property.


## -syntax


````
NTSTATUS WdfFdoInitQueryProperty(
  _In_  PWDFDEVICE_INIT          DeviceInit,
  _In_  DEVICE_REGISTRY_PROPERTY DeviceProperty,
  _In_  ULONG                    BufferLength,
  _Out_ PVOID                    PropertyBuffer,
  _Out_ PULONG                   ResultLength
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.


### -param DeviceProperty [in]

A <a href="https://msdn.microsoft.com/a17b4a88-45e8-45e7-b879-2f41b97be368">DEVICE_REGISTRY_PROPERTY</a>-typed enumerator value that identifies the device property to be retrieved.


### -param BufferLength [in]

The size, in bytes, of the buffer that is pointed to by <i>PropertyBuffer</i>.


### -param PropertyBuffer [out]

A caller-supplied pointer to a caller-allocated buffer that receives the requested device property. This pointer can be <b>NULL</b> if the <i>BufferLength</i> parameter is zero.


### -param ResultLength [out]

A caller-supplied location that, on return, contains the size, in bytes, of the information that <b>WdfFdoInitQueryProperty</b> stored in <i>PropertyBuffer</i>. If this method's return value is STATUS_BUFFER_TOO_SMALL, <i>ResultLength</i> receives the required buffer size.


## -returns



If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The supplied buffer is too small to receive the information.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>DeviceProperty</i> value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure was not obtained from the driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.

</td>
</tr>
</table>
 

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



Before receiving device property data, drivers typically must make an initial call to <b>WdfFdoInitQueryProperty</b> to obtain the required buffer size. For some properties, the data size can change between the time that the required size is returned and the time that the driver calls this routine again. Therefore, drivers should call <b>WdfFdoInitQueryProperty</b> inside a loop that executes until the return status is not STATUS_BUFFER_TOO_SMALL. 

It is best to use <b>WdfFdoInitQueryProperty</b> only if the required buffer size is known and unchanging, because in that case the driver has to call <b>WdfFdoInitQueryProperty</b> only once. If the required buffer size is unknown or varies, the driver should call <a href="..\wdffdo\nf-wdffdo-wdffdoinitallocandqueryproperty.md">WdfFdoInitAllocAndQueryProperty</a>. 

The driver can call <b>WdfFdoInitQueryProperty</b> only before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

After calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, a driver can obtain device property information by calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryproperty.md">WdfDeviceQueryProperty</a>.

For more information about the <b>WdfFdoInitQueryProperty</b> method, see <a href="https://msdn.microsoft.com/3b988f6d-c50e-412d-85cb-031746535ff4">Creating Device Objects in a Function Driver</a>.

Alternatively, you can use <a href="..\wdffdo\nf-wdffdo-wdffdoinitquerypropertyex.md">WdfFdoInitQueryPropertyEx</a> to access device properties that are exposed through the Unified Property Model.


#### Examples

The following code example obtains a Unicode string that represents the name of a device's enumerator and returns <b>TRUE</b> if the string is "PCI".

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status = STATUS_SUCCESS;
WCHAR  enumeratorName[64] = {0};
ULONG  returnSize;
UNICODE_STRING  unicodeEnumName, temp;

status = WdfFdoInitQueryProperty(
                                 DeviceInit,
                                 DevicePropertyEnumeratorName,
                                 sizeof(enumeratorName),
                                 enumeratorName,
                                 &amp;returnSize
                                 );
if(!NT_SUCCESS(status)){
    return status;
}

RtlInitUnicodeString(
                     &amp;unicodeEnumName,
                     enumeratorName
                     );
RtlInitUnicodeString(
                     &amp;temp,
                     L"PCI"
                     );
if(RtlCompareUnicodeString(
                           &amp;unicodeEnumName,
                           &amp;temp,
                           TRUE
                           ) == 0) {
    //
    // This device is a PCI device.
    //
    return TRUE;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdffdo\nf-wdffdo-wdffdoinitallocandqueryproperty.md">WdfFdoInitAllocAndQueryProperty</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryproperty.md">WdfDeviceQueryProperty</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoInitQueryProperty method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

