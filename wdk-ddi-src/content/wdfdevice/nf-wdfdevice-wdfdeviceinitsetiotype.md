---
UID: NF:wdfdevice.WdfDeviceInitSetIoType
title: WdfDeviceInitSetIoType function
author: windows-driver-content
description: The WdfDeviceInitSetIoType method sets the method or preference for how a driver will access the data buffers that are included in read and write requests for a specified device.
old-location: wdf\wdfdeviceinitsetiotype.htm
old-project: wdf
ms.assetid: fcad4b8e-4273-43ff-8077-a96d1bd4640a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceInitSetIoType, kmdf.wdfdeviceinitsetiotype, DFDeviceObjectGeneralRef_4c821466-f1d7-46fa-a1f0-e8fefd20caab.xml, WdfDeviceInitSetIoType method, PFN_WDFDEVICEINITSETIOTYPE, wdfdevice/WdfDeviceInitSetIoType, wdf.wdfdeviceinitsetiotype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfDeviceInitSetIoType
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetIoType function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceInitSetIoType</b> method sets the method or preference for how a driver will access the data buffers that are included in read and write requests for a specified device.


## -syntax


````
void WdfDeviceInitSetIoType(
  _In_ PWDFDEVICE_INIT    DeviceInit,
  _In_ WDF_DEVICE_IO_TYPE IoType
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param IoType [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed enumerator that identifies the method that the driver will use to access data buffers that it receives for read and write requests.


## -returns


This method does not return a value.



## -remarks


<b>KMDF </b>If you are writing a new driver using KMDF version 1.13 or later, you should instead use <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetiotypeex.md">WdfDeviceInitSetIoTypeEx</a>. Calling <b>WdfDeviceInitSetIoType</b> from a KMDF filter driver has no effect. For filter drivers, the framework uses the I/O type specified by the next-lower driver in the driver stack.

<b>UMDF </b>If you are converting a KMDF driver that calls <b>WdfDeviceInitSetIoType</b> to UMDF version 2.0 or later, your converted driver can continue to call <b>WdfDeviceInitSetIoType</b> without issue. However, if you are writing an entirely  new driver using UMDF version 2.0 or later, you should instead use <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetiotypeex.md">WdfDeviceInitSetIoTypeEx</a>.

If a driver calls <b>WdfDeviceInitSetIoType</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

If the driver does not call <b>WdfDeviceInitSetIoType</b>, the framework sets the driver's buffer-access method to <b>WdfDeviceIoBuffered</b>, for the specified device.

For more information about buffer-access methods, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers</a>.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetiotypeex.md">WdfDeviceInitSetIoTypeEx</a>

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>

<a href="https://msdn.microsoft.com/7d79f34d-42aa-4ac7-a63d-2f17ee0dfcf0"> IWDFDeviceInitialize2::SetIoTypePreference</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitSetIoType method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

