---
UID: NF:wdffdo.WdfFdoInitQueryPropertyEx
title: WdfFdoInitQueryPropertyEx function (wdffdo.h)
description: The WdfFdoInitQueryPropertyEx method retrieves a specified device property.
old-location: wdf\wdffdoinitquerypropertyex.htm
tech.root: wdf
ms.assetid: C8377EE4-A7A1-4063-A7DC-53D0D8C6E0C3
ms.date: 02/26/2018
ms.keywords: WdfFdoInitQueryPropertyEx, WdfFdoInitQueryPropertyEx method, wdf.wdffdoinitquerypropertyex, wdffdo/WdfFdoInitQueryPropertyEx
ms.topic: function
f1_keywords:
 - "wdffdo/WdfFdoInitQueryPropertyEx"
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.ddi-compliance: 
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
- WdfFdoInitQueryPropertyEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFdoInitQueryPropertyEx function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfFdoInitQueryPropertyEx</b> method retrieves a specified device property.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.


### -param DeviceProperty [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure that identifies the device property to be retrieved.


### -param BufferLength [in]

The size, in bytes, of the buffer that is pointed to by <i>PropertyBuffer</i>.


### -param PropertyBuffer [out]

A caller-supplied pointer to a caller-allocated buffer that receives the requested information. The pointer can be <b>NULL</b> if the <i>BufferLength</i> parameter is zero.


### -param ResultLength [out]

A caller-supplied location that, on return, contains the 
                  size, in bytes, of the information that the method stored in 
                  <i>PropertyBuffer</i>. If the function's return value is 
                  <b>STATUS_BUFFER_TOO_SMALL</b>, this location receives the required 
                  buffer size.


### -param Type [out]

A pointer to a <b>DEVPROPTYPE</b> variable that, on return, contains the property type value
                  of the property 
                  data stored in <i>PropertyBuffer</i>.


## -returns



If the operation succeeds, <b>WdfFdoInitQueryPropertyEx</b> returns STATUS_SUCCESS. Additional return values include:

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>DeviceProperty</i> value is invalid.

</td>
</tr>
</table>
 

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Before receiving device property data, drivers typically call the <b>WdfFdoInitQueryPropertyEx</b> method just to obtain the required buffer size. For some properties, the data size can change between when the required size is returned and when the driver calls <b>WdfFdoInitQueryPropertyEx</b> again. Therefore, drivers should call <b>WdfFdoInitQueryPropertyEx</b> inside a loop that executes until the return status is not STATUS_BUFFER_TOO_SMALL. 

It is best to use <b>WdfFdoInitQueryPropertyEx</b> only if the required buffer size is known and unchanging, because in that case the driver has to call <b>WdfFdoInitQueryPropertyEx</b> only once. If the required buffer size is unknown or varies, the driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitallocandquerypropertyex">WdfFdoInitAllocAndQueryPropertyEx</a>. 

The driver can call <b>WdfFdoInitQueryPropertyEx</b> only before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

After calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>, a driver can obtain device property information by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicequerypropertyex">WdfDeviceQueryPropertyEx</a>.

For information about related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-the-unified-device-property-model">Accessing the Unified Device Property Model</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitqueryproperty">WdfFdoInitQueryProperty</a>
 

 

