---
UID: NF:wdfdevice.WdfDeviceSetCharacteristics
title: WdfDeviceSetCharacteristics function (wdfdevice.h)
description: The WdfDeviceSetCharacteristics method sets device characteristics for a specified device.
old-location: wdf\wdfdevicesetcharacteristics.htm
tech.root: wdf
ms.assetid: 07b5d7ed-fc4c-45e5-8748-2630c91d912a
ms.date: 02/26/2018
keywords: ["WdfDeviceSetCharacteristics function"]
ms.keywords: DFDeviceObjectGeneralRef_a5d23cdb-a42e-48ef-9158-174354e13ca6.xml, WdfDeviceSetCharacteristics, WdfDeviceSetCharacteristics method, kmdf.wdfdevicesetcharacteristics, wdf.wdfdevicesetcharacteristics, wdfdevice/WdfDeviceSetCharacteristics
f1_keywords:
 - "wdfdevice/WdfDeviceSetCharacteristics"
 - "WdfDeviceSetCharacteristics"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceSetCharacteristics
targetos: Windows
req.typenames: 
---

# WdfDeviceSetCharacteristics function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceSetCharacteristics</b> method sets device characteristics for a specified device.


## -parameters




### -param Device 
[in]
A handle to a framework device object.


### -param DeviceCharacteristics 
[in]
A value that consists of ORed system-defined constants that represent device characteristics. For more information, see the <b>Characteristics</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




You should set device characteristics by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetcharacteristics">WdfDeviceInitSetCharacteristics</a> method in your <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. If your driver cannot determine a device's characteristics until after the <i>EvtDriverDeviceAdd</i> callback function returns, the driver typically should call <b>WdfDeviceSetCharacteristics</b> in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function.

Each call to <b>WdfDeviceSetCharacteristics</b> overwrites the settings of any previous call.


#### Examples

The following code example sets the FILE_REMOVABLE_MEDIA characteristic for a specified device.

```cpp
WdfDeviceSetCharacteristics(
                            Device,
                            FILE_REMOVABLE_MEDIA
                            );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetcharacteristics">WdfDeviceGetCharacteristics</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetcharacteristics">WdfDeviceInitSetCharacteristics</a>
 

 

