---
UID: NF:wdfdevice.WdfDevStateIsNP
title: WdfDevStateIsNP function (wdfdevice.h)
description: The WdfDevStateIsNP method returns a Boolean value that indicates whether a specified power state or power policy state is a nonpageable state.
old-location: wdf\wdfdevstateisnp.htm
tech.root: wdf
ms.assetid: 49584600-e470-4be8-9111-3e890a9fedfd
ms.date: 02/26/2018
keywords: ["WdfDevStateIsNP function"]
ms.keywords: DFDeviceObjectGeneralRef_ed6dd7ac-b5e3-49b2-a4d8-08e4e9377321.xml, WdfDevStateIsNP, WdfDevStateIsNP method, kmdf.wdfdevstateisnp, wdf.wdfdevstateisnp, wdfdevice/WdfDevStateIsNP
f1_keywords:
 - "wdfdevice/WdfDevStateIsNP"
 - "WdfDevStateIsNP"
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
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
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
- WdfDevStateIsNP
targetos: Windows
req.typenames: 
---

# WdfDevStateIsNP function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDevStateIsNP</b> method returns a Boolean value that indicates whether a specified power state or power policy state is a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">nonpageable</a> state. 


## -parameters




### -param State [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_power_state">WDF_DEVICE_POWER_STATE</a>-typed enumerator or a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_power_policy_state">WDF_DEVICE_POWER_POLICY_STATE</a>-typed enumerator.


## -returns



If the calling driver is currently nonpageable, the <b>WdfDevStateIsNP</b> method returns <b>TRUE</b>. Otherwise, the method returns <b>FALSE</b>.




## -remarks



To obtain the current state of the framework's power state machine, a driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepowerstate">WdfDeviceGetDevicePowerState</a> from within a PnP or power callback function. To obtain the current state of the framework's power policy state machine, a driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepowerpolicystate">WdfDeviceGetDevicePowerPolicyState</a> from within a power policy callback function. After the driver has called <b>WdfDeviceGetDevicePowerState</b> or <b>WdfDeviceGetDevicePowerPolicyState</b>, it can call <b>WdfDevStateIsNP</b> to determine if the returned state represents a pageable or nonpageable state. If the framework's state machine is in a nonpageable state, the driver is not pageable and must not perform any operations that might cause the operating system to access the paging file. Such operations include accessing files, the registry, or paged pool. 


#### Examples

The following code example sets the <b>nonpageable</b> value to <b>TRUE</b> if the framework's power state machine is currently in a nonpageable state.

```cpp
BOOLEAN nonpageable;

nonpageable = WdfDevStateIsNP(WdfDeviceGetDevicePowerState(device));
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowernotpageable">WdfDeviceInitSetPowerNotPageable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a>
 

 

