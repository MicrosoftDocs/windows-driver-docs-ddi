---
UID: NF:wdfdevice.WdfDeviceInitSetDeviceType
title: WdfDeviceInitSetDeviceType function
author: windows-driver-content
description: The WdfDeviceInitSetDeviceType method sets the device type for a specified device.
old-location: wdf\wdfdeviceinitsetdevicetype.htm
old-project: wdf
ms.assetid: 26c5c998-fb10-45c3-b28c-91a759fa941e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdevice/WdfDeviceInitSetDeviceType, WdfDeviceInitSetDeviceType method, wdf.wdfdeviceinitsetdevicetype, DFDeviceObjectGeneralRef_872eb4dd-0d40-46ed-a7ed-4eae8ec67240.xml, kmdf.wdfdeviceinitsetdevicetype, PFN_WDFDEVICEINITSETDEVICETYPE, WdfDeviceInitSetDeviceType
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
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
apiname:
-	WdfDeviceInitSetDeviceType
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetDeviceType function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitSetDeviceType</b> method sets the device type for a specified device.


## -syntax


````
VOID WdfDeviceInitSetDeviceType(
  _In_ PWDFDEVICE_INIT DeviceInit,
  _In_ DEVICE_TYPE     DeviceType
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param DeviceType [in]

A FILE_DEVICE_XXXX value that identifies the device type. For more information about FILE_DEVICE_XXXX values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>.


## -returns


None



## -remarks


If a driver calls <b>WdfDeviceInitSetDeviceType</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

For more information about calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

The device type that a driver specifies determines the default priority boost value that the framework uses when the driver completes an I/O request. For more information about priority boost values, see <a href="https://msdn.microsoft.com/9a501ca1-58c9-4458-b202-9581f8ce5e5f">Specifying Priority Boosts When Completing I/O Requests</a>.


      If you are writing a UMDF driver, you  must modify your driver's INF file or make registry changes to specify a device type. For more information about using the registry, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563759">Setting Device Object Registry Properties During Installation</a>.


