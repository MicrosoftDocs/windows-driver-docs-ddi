---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SURPRISE_REMOVAL
title: EVT_WDF_DEVICE_SURPRISE_REMOVAL (wdfdevice.h)
description: A driver's EvtDeviceSurpriseRemoval event callback function performs any operations that are needed after a device has been unexpectedly removed from the system or after a driver reports that the device has failed.
old-location: wdf\evtdevicesurpriseremoval.htm
tech.root: wdf
ms.assetid: 0fa0eb7e-7fbb-4838-b1d7-ef5a9d5024d4
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_SURPRISE_REMOVAL callback function"]
ms.keywords: DFDeviceObjectGeneralRef_3623a2b6-f452-4e7d-98a3-d9e42d815f35.xml, EVT_WDF_DEVICE_SURPRISE_REMOVAL, EVT_WDF_DEVICE_SURPRISE_REMOVAL callback, EvtDeviceSurpriseRemoval, EvtDeviceSurpriseRemoval callback function, kmdf.evtdevicesurpriseremoval, wdf.evtdevicesurpriseremoval, wdfdevice/EvtDeviceSurpriseRemoval
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DEVICE_SURPRISE_REMOVAL
 - wdfdevice/EVT_WDF_DEVICE_SURPRISE_REMOVAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtDeviceSurpriseRemoval
---

# EVT_WDF_DEVICE_SURPRISE_REMOVAL callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceSurpriseRemoval</i> event callback function performs any operations that are needed after a device has been unexpectedly removed from the system or after a driver reports that <a href="/windows-hardware/drivers/wdf/reporting-device-failures">the device has failed</a>.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

## -remarks

To register an <i>EvtDeviceSurpriseRemoval</i> callback function, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

The framework does not synchronize the <i>EvtDeviceSurpriseRemoval</i> callback function with other PnP and power management callback functions. For information about how the framework synchronizes the execution of a driver's event callback functions, see <a href="/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>. 

For more information about when the framework calls this callback function, and for more information about synchronization issues, see <a href="/windows-hardware/drivers/wdf/a-user-unplugs-a-device">A User Unplugs a Device</a>.