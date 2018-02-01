---
UID: NF:wdfdevice.WdfDeviceSetFailed
title: WdfDeviceSetFailed function
author: windows-driver-content
description: The WdfDeviceSetFailed method informs the framework that the driver encountered a hardware or software error that is associated with a specified device.
old-location: wdf\wdfdevicesetfailed.htm
old-project: wdf
ms.assetid: 87fbceab-d08c-4da7-a257-1454f84c04b7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceSetFailed method, WdfDeviceSetFailed, kmdf.wdfdevicesetfailed, wdfdevice/WdfDeviceSetFailed, PFN_WDFDEVICESETFAILED, DFDeviceObjectGeneralRef_7efacd41-7c8c-4832-b10a-cc7d3dac8982.xml, wdf.wdfdevicesetfailed
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
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
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfDeviceSetFailed
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceSetFailed function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceSetFailed</b> method informs the framework that the driver encountered a hardware or software error that is associated with a specified device.


## -syntax


````
VOID WdfDeviceSetFailed(
  _In_ WDFDEVICE                Device,
  _In_ WDF_DEVICE_FAILED_ACTION FailedAction
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param FailedAction [in]

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_failed_action.md">WDF_DEVICE_FAILED_ACTION</a>-typed enumerator that indicates whether the framework should attempt to reload the specified device's drivers.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


If a driver encounters an unrecoverable hardware or software error, it must call <b>WdfDeviceSetFailed</b> so that the system can unload the device's drivers.

Starting in UMDF version 2.15, a UMDF driver can request that the the underlying bus driver re-enumerate it by calling <b>WdfDeviceSetFailed</b> with <i>FailedAction</i> set to <b>WdfDeviceFailedAttemptRestart</b>. The bus driver must support the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546570">GUID_REENUMERATE_SELF_INTERFACE_STANDARD</a> interface.

Alternatively, a UMDF driver can set <i>FailedAction</i> to <b>WdfDeviceFailedNoRestart</b>.

For more information about <b>WdfDeviceSetFailed</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.


