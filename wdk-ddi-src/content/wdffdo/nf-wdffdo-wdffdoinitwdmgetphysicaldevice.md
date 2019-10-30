---
UID: NF:wdffdo.WdfFdoInitWdmGetPhysicalDevice
title: WdfFdoInitWdmGetPhysicalDevice function (wdffdo.h)
description: The WdfFdoInitWdmGetPhysicalDevice method retrieves a device's WDM physical device object (PDO).
old-location: wdf\wdffdoinitwdmgetphysicaldevice.htm
tech.root: wdf
ms.assetid: eba64244-50ff-4c59-a30f-46874c683e63
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_49386e60-3427-449c-8c36-fe2e8bc7fabb.xml, WdfFdoInitWdmGetPhysicalDevice, WdfFdoInitWdmGetPhysicalDevice method, kmdf.wdffdoinitwdmgetphysicaldevice, wdf.wdffdoinitwdmgetphysicaldevice, wdffdo/WdfFdoInitWdmGetPhysicalDevice
ms.topic: function
f1_keywords:
 - "wdffdo/WdfFdoInitWdmGetPhysicalDevice"
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfFdoInitWdmGetPhysicalDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFdoInitWdmGetPhysicalDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfFdoInitWdmGetPhysicalDevice</b> method retrieves a device's WDM physical device object (PDO).


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.


## -returns



If the operation succeeds, the method returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. Otherwise the method returns <b>NULL</b>.




## -remarks



The driver must call <b>WdfFdoInitWdmGetPhysicalDevice</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about the <b>WdfFdoInitWdmGetPhysicalDevice</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-device-objects-in-a-function-driver">Creating Device Objects in a Function Driver</a>.


#### Examples

The following code example obtains a pointer to a DEVICE_OBJECT structure that represents a device's WDM PDO.

```cpp
PDEVICE_OBJECT device;

device = WdfFdoInitWdmGetPhysicalDevice(DeviceInit);
```


