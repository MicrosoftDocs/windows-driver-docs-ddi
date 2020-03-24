---
UID: NF:wdfpdo.WdfPdoInitRemovePowerDependencyOnParent
title: WdfPdoInitRemovePowerDependencyOnParent
ms.date: 03/24/2020
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdfpdo.h
req.idl: 
req.include-header: Wdf.h
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 1.29
req.lib: Wdf01000.sys (KMDF)
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
 - WdfPdoInitRemovePowerDependencyOnParent
f1_keywords:
 - wdfpdo/WdfPdoInitRemovePowerDependencyOnParent
dev_langs:
 - c++
---

## -description

The **WdfPdoInitRemovePowerDependencyOnParent** method removes the power dependency described in the **Remarks** section.

## -parameters

### -param DeviceInit

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.

## -remarks

In general, the framework requires that a parent bus driver enter the D0 device power state before a child device enters D0, and similarly that a child device exit D0 before the parent leaves D0.

However, this behavior may not be desired, in particular if the child device is a virtual device that doesn't represent any real hardware. At S0 idle power-down, the power state of the child device may not be relevant to the parent. In fact, the child device may have no reason to perform S0 idle detection. In this case, it would be better for the parent device to transition between D0 and Dx based on I/O activity, rather than being dependent on the power state of the child device.

Removing the power dependency has the following effects on the bus driver:

* The PDO PnP/Power callbacks might execute while the parent device is in Dx.
* The PDO enable/disable-wake-at-bus callbacks might execute while the parent device is in Dx.
* A request forwarded from a power-managed queue on the PDO (assuming the PDO is the power policy owner) to a non power-managed queue on the FDO might be dispatched while the bus driver is in Dx.
* The child stack performs power state transitions independently of the parent stack. This includes scenarios such as fast-resume in which the child stack might receive its S-IRP and even finish processing its D-IRP before the parent stack finishes processing its own D-IRP.

To remove the power dependency, the bus driver can call **WdfPdoInitRemovePowerDependencyOnParent** when it creates the PDO for the child device.

This function takes no action if the parent bus driver is not the power policy owner of the parent device stack.

## -see-also

