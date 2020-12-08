---
UID: NF:wdfdevice.WdfDeviceInitSetPowerPolicyOwnership
title: WdfDeviceInitSetPowerPolicyOwnership function (wdfdevice.h)
description: The WdfDeviceInitSetPowerPolicyOwnership method establishes whether the calling driver is, or is not, the power policy owner for a specified device.
old-location: wdf\wdfdeviceinitsetpowerpolicyownership.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfDeviceInitSetPowerPolicyOwnership function"]
ms.keywords: DFDeviceObjectGeneralRef_0c94f8f0-3b23-404a-83c2-1742785ff17d.xml, WdfDeviceInitSetPowerPolicyOwnership, WdfDeviceInitSetPowerPolicyOwnership method, kmdf.wdfdeviceinitsetpowerpolicyownership, wdf.wdfdeviceinitsetpowerpolicyownership, wdfdevice/WdfDeviceInitSetPowerPolicyOwnership
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, FDOPowerPolicyOwnerAPI, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceInitSetPowerPolicyOwnership
 - wdfdevice/WdfDeviceInitSetPowerPolicyOwnership
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
 - WdfDeviceInitSetPowerPolicyOwnership
---

# WdfDeviceInitSetPowerPolicyOwnership function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceInitSetPowerPolicyOwnership</b> method establishes whether the calling driver is, or is not, the power policy owner for a specified device.

## -parameters

### -param DeviceInit 

[in]
A caller-supplied pointer to a <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.

### -param IsPowerPolicyOwner 

[in]
A Boolean value that indicates whether the calling driver is the power policy owner. If <b>TRUE</b>, the calling driver is the power policy owner. If <b>FALSE</b>, it is not the power policy owner.

## -remarks

If you are writing a framework-based function driver, the framework automatically establishes your driver as the power policy owner. (If the device operates in raw mode, the bus driver is the default power policy owner.) 

To change the default power policy owner, the following two drivers must call <b>WdfDeviceInitSetPowerPolicyOwnership</b>:

<ul>
<li>
The default power policy owner must call <b>WdfDeviceInitSetPowerPolicyOwnership</b> with <i>IsPowerPolicyOwner</i> set to <b>FALSE</b>.

</li>
<li>
The driver that you want to be the power policy owner must call <b>WdfDeviceInitSetPowerPolicyOwnership</b> with <i>IsPowerPolicyOwner</i> set to <b>TRUE</b>.

</li>
</ul>
If you are writing a framework-based bus driver or filter driver, and if the device does not operate in raw mode, your driver will not be the power policy owner unless it calls <b>WdfDeviceInitSetPowerPolicyOwnership</b>. 

Only one driver in each stack can be the power policy owner, so you must ensure that only one driver calls <b>WdfDeviceInitSetPowerPolicyOwnership</b> with <i>IsPowerPolicyOwner</i> set to <b>TRUE</b>.

If your driver calls <b>WdfDeviceInitSetPowerPolicyOwnership</b>, it must do so before it calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information, see <a href="/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about calling <b>WdfDeviceInitSetPowerPolicyOwnership</b>, see <a href="/windows-hardware/drivers/wdf/power-policy-ownership">Power Policy Ownership</a>.


#### Examples

The following code example is from the <a href="/windows-hardware/drivers/wdf/sample-kmdf-drivers">Serial</a> sample driver. This example checks a registry value to determine if a driver should be the power policy owner. If the driver should not be the power policy owner, the example calls <b>WdfDeviceInitSetPowerPolicyOwnership</b>.

```cpp
//
// Call subroutine that checks a registry value.
//
SerialGetFdoRegistryKeyValue(
                             DeviceInit,
                             L"SerialRelinquishPowerPolicy",
                             &relinquishPowerPolicy
                             );
//
// If the registry value is TRUE, do not own power policy.
//
if(relinquishPowerPolicy) {
    WdfDeviceInitSetPowerPolicyOwnership(
                                         DeviceInit,
                                         FALSE
                                         );
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>
