---
UID: NF:wdfdevice.WdfDeviceCreateDeviceInterface
title: WdfDeviceCreateDeviceInterface function (wdfdevice.h)
description: The WdfDeviceCreateDeviceInterface method creates a device interface for a specified device.
old-location: wdf\wdfdevicecreatedeviceinterface.htm
tech.root: wdf
ms.assetid: cdfe1932-ee3d-41ea-8d7b-85c17c0f1722
ms.date: 02/26/2018
keywords: ["WdfDeviceCreateDeviceInterface function"]
ms.keywords: DFDeviceObjectGeneralRef_467c4866-4ba7-4450-9aec-e63c3172d604.xml, WdfDeviceCreateDeviceInterface, WdfDeviceCreateDeviceInterface method, kmdf.wdfdevicecreatedeviceinterface, wdf.wdfdevicecreatedeviceinterface, wdfdevice/WdfDeviceCreateDeviceInterface
f1_keywords:
 - "wdfdevice/WdfDeviceCreateDeviceInterface"
req.header: wdfdevice.h
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
- WdfDeviceCreateDeviceInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceCreateDeviceInterface function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceCreateDeviceInterface</b> method creates a device interface for a specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param InterfaceClassGUID [in]

A pointer to a GUID that identifies the device interface class.


### -param ReferenceString [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that describes a reference string for the device interface. The string must not contain any path separator characters ("/" or "\\").  This parameter is optional and can be <b>NULL</b>.   For more information, see the following Remarks section.


## -returns



<b>WdfDeviceCreateDeviceInterface</b> returns STATUS_SUCCESS if the operation succeeds.

For a list of other return values that <b>WdfDeviceCreateDeviceInterface</b> can return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Drivers can use the <i>ReferenceString</i> parameter to differentiate different instances of a single interface. In other words, if a driver calls <b>WdfDeviceCreateDeviceInterface</b> twice for the same device interface class, the driver can specify a different <i>ReferenceString</i> parameter each time. When an instance of an interface is opened, the I/O manager passes the instance's reference string to the driver. The reference string is appended to the path component of the interface instance's name. The driver can then use the reference string to determine which instance of the device interface class is being opened.

For more information about device interfaces and the <b>WdfDeviceCreateDeviceInterface</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces">Using Device Interfaces</a>.


#### Examples

The following example registers the COM port interface class for a device.

```cpp
NTSTATUS  status;

status = WdfDeviceCreateDeviceInterface(
                                        Device,
                                        (LPGUID) &GUID_DEVINTERFACE_COMPORT,
                                        NULL
                                        );
```



## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetdeviceinterfacestate">WdfDeviceSetDeviceInterfaceState</a>
 

 

