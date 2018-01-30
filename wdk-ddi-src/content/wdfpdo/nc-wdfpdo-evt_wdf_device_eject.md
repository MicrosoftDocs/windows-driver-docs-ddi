---
UID: NC:wdfpdo.EVT_WDF_DEVICE_EJECT
title: EVT_WDF_DEVICE_EJECT
author: windows-driver-content
description: A driver's EvtDeviceEject event callback function handles operations that are necessary to eject a device from its docking station.
old-location: wdf\evtdeviceeject.htm
old-project: wdf
ms.assetid: fc3f3a15-9a79-4275-9ba4-b01ab8851390
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdeviceeject, EvtDeviceEject callback function, EvtDeviceEject, EVT_WDF_DEVICE_EJECT, EVT_WDF_DEVICE_EJECT, wdfpdo/EvtDeviceEject, DFDeviceObjectFdoPdoRef_38feba70-59b4-4981-af2d-0fc0fa4ff68a.xml, kmdf.evtdeviceeject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfpdo.h
apiname:
-	EvtDeviceEject
product: Windows
targetos: Windows
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_EJECT callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtDeviceEject</i> event callback function handles operations that are necessary to eject a device from its docking station.


## -prototype


````
EVT_WDF_DEVICE_EJECT EvtDeviceEject;

NTSTATUS EvtDeviceEject(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns


If the operation succeeds, the driver must return STATUS_SUCCESS. Otherwise it must return an NTSTATUS value that <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a> evaluates as <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.

For more information about return values, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.



## -remarks


Framework-based bus drivers can provide an <i>EvtDeviceEject</i> callback function. A bus driver must provide an <i>EvtDeviceEject</i> callback function if the driver must perform operations that physically eject one of its enumerated child devices from the device's docking station. To register this callback function, the bus driver must call <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitseteventcallbacks.md">WdfPdoInitSetEventCallbacks</a>.

Before calling the <i>EvtDeviceEject</i> callback function, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a> and <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback functions.

If a driver's <i>EvtDeviceEject</i> callback function returns STATUS_SUCCESS, the framework updates the driver's child list to indicate that the ejected device is no longer available. Therefore the driver does not have to call <a href="..\wdfpdo\nf-wdfpdo-wdfpdomarkmissing.md">WdfPdoMarkMissing</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistupdatechilddescriptionasmissing.md">WdfChildListUpdateChildDescriptionAsMissing</a>.

For more information about device ejection, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.



## -see-also

<a href="..\wdfpdo\nc-wdfpdo-evt_wdf_device_set_lock.md">EvtDeviceSetLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_EJECT callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

