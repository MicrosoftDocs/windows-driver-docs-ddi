---
UID: NF:wdfdevice.WdfDeviceSetCharacteristics
title: WdfDeviceSetCharacteristics function
author: windows-driver-content
description: The WdfDeviceSetCharacteristics method sets device characteristics for a specified device.
old-location: wdf\wdfdevicesetcharacteristics.htm
old-project: wdf
ms.assetid: 07b5d7ed-fc4c-45e5-8748-2630c91d912a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfdevicesetcharacteristics, DFDeviceObjectGeneralRef_a5d23cdb-a42e-48ef-9158-174354e13ca6.xml, kmdf.wdfdevicesetcharacteristics, PFN_WDFDEVICESETCHARACTERISTICS, WdfDeviceSetCharacteristics, wdfdevice/WdfDeviceSetCharacteristics, WdfDeviceSetCharacteristics method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceSetCharacteristics
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceSetCharacteristics function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceSetCharacteristics</b> method sets device characteristics for a specified device.


## -syntax


````
VOID WdfDeviceSetCharacteristics(
  _In_ WDFDEVICE Device,
  _In_ ULONG     DeviceCharacteristics
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DeviceCharacteristics [in]

A value that consists of ORed system-defined constants that represent device characteristics. For more information, see the <b>Characteristics</b> member of the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


You should set device characteristics by calling the <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetcharacteristics.md">WdfDeviceInitSetCharacteristics</a> method in your <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. If your driver cannot determine a device's characteristics until after the <i>EvtDriverDeviceAdd</i> callback function returns, the driver typically should call <b>WdfDeviceSetCharacteristics</b> in its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function.

Each call to <b>WdfDeviceSetCharacteristics</b> overwrites the settings of any previous call.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetcharacteristics.md">WdfDeviceInitSetCharacteristics</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetcharacteristics.md">WdfDeviceGetCharacteristics</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceSetCharacteristics method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

