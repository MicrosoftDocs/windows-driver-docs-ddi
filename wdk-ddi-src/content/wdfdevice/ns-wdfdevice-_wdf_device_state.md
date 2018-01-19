---
UID: NS:wdfdevice._WDF_DEVICE_STATE
title: _WDF_DEVICE_STATE
author: windows-driver-content
description: The WDF_DEVICE_STATE structure specifies a device's Plug and Play state.
old-location: wdf\wdf_device_state.htm
old-project: wdf
ms.assetid: 5d0a2303-df2b-45fe-9c88-df4bb19a2a9f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDF_DEVICE_STATE, *PWDF_DEVICE_STATE, WDF_DEVICE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_DEVICE_STATE
req.alt-loc: wdfdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PWDF_DEVICE_STATE, WDF_DEVICE_STATE
req.product: Windows 10 or later.
---

# _WDF_DEVICE_STATE structure



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_DEVICE_STATE</b> structure specifies a device's Plug and Play state.



## -syntax

````
typedef struct _WDF_DEVICE_STATE {
  ULONG         Size;
  WDF_TRI_STATE Disabled;
  WDF_TRI_STATE DontDisplayInUI;
  WDF_TRI_STATE Failed;
  WDF_TRI_STATE NotDisableable;
  WDF_TRI_STATE Removed;
  WDF_TRI_STATE ResourcesChanged;
} WDF_DEVICE_STATE, *PWDF_DEVICE_STATE;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field Disabled

A <a href="..\wdftypes\ne-wdftypes-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device is disabled. For more information about the <b>WDF_TRI_STATE</b> type, see the following Remarks section.


### -field DontDisplayInUI

A <a href="..\wdftypes\ne-wdftypes-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device is hidden (not displayed) in Device Manager. For more information, see <a href="https://msdn.microsoft.com/5dd02478-9937-4364-bd33-b64ac89c32eb">Viewing Hidden Devices</a>. (After you set this member to <b>WdfTrue</b>, changing its value has no effect.)


### -field Failed

A <a href="..\wdftypes\ne-wdftypes-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device is present but has failed.


### -field NotDisableable

A <a href="..\wdftypes\ne-wdftypes-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device cannot be disabled.


### -field Removed

A <a href="..\wdftypes\ne-wdftypes-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device has been removed.


### -field ResourcesChanged

A <a href="..\wdftypes\ne-wdftypes-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device's resource requirements have changed.


## -remarks
Structure members use the <a href="..\wdftypes\ne-wdftypes-_wdf_tri_state.md">WDF_TRI_STATE</a> type. A value of <b>WdfUseDefault</b> indicates the framework will use the value that was provided by a lower driver in the stack. For example, if a bus driver specifies <b>WdfTrue</b> for <b>NotDisableable</b> and the device's function driver specifies <b>WdfUseDefault</b>, the framework uses <b>WdfTrue</b> for the device state.

The <b>WDF_DEVICE_STATE</b> structure is used as a parameter to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetdevicestate.md">WdfDeviceSetDeviceState</a> and <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicestate.md">WdfDeviceGetDeviceState</a>.

To initialize a <b>WDF_DEVICE_STATE</b> structure, the driver must call <a href="..\wdfdevice\nf-wdfdevice-wdf_device_state_init.md">WDF_DEVICE_STATE_INIT</a>.

For more information about the members of the <b>WDF_DEVICE_STATE</b> structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559618">PNP_DEVICE_STATE</a>.</p>