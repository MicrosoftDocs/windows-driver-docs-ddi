---
UID: NF:wdm.IoInvalidateDeviceState
title: IoInvalidateDeviceState function (wdm.h)
description: The IoInvalidateDeviceState routine notifies the PnP manager that some aspect of the PnP state of a device has changed.
old-location: kernel\ioinvalidatedevicestate.htm
tech.root: kernel
ms.assetid: ca27e8d3-80ee-467c-9c88-19770cd86d94
ms.date: 04/30/2018
keywords: ["IoInvalidateDeviceState function"]
ms.keywords: IoInvalidateDeviceState, IoInvalidateDeviceState routine [Kernel-Mode Driver Architecture], k104_05ef79e6-a7d1-4de4-aefa-5aa7d9121f04.xml, kernel.ioinvalidatedevicestate, wdm/IoInvalidateDeviceState
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoInvalidateDeviceState
 - wdm/IoInvalidateDeviceState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoInvalidateDeviceState
---

# IoInvalidateDeviceState function


## -description

The <b>IoInvalidateDeviceState</b> routine notifies the PnP manager that some aspect of the PnP state of a device has changed.

## -parameters

### -param PhysicalDeviceObject 

[in]
Pointer to the PDO for the device.

## -remarks

Drivers call this routine to indicate that something has changed with respect to one of the following aspects of a device's PnP state:

PNP_DEVICE_DISABLED

PNP_DEVICE_DONT_DISPLAY_IN_UI

PNP_DEVICE_FAILED

PNP_DEVICE_NOT_DISABLEABLE

PNP_DEVICE_REMOVED

PNP_DEVICE_RESOURCE_REQUIREMENTS_CHANGED

For descriptions of the preceding constants, see [PNP_DEVICE_STATE](/windows-hardware/drivers/kernel/handling-an-irp-mn-surprise-removal-request#about-pnpdevicestate).

In response to this routine, the PnP manager sends an <a href="/windows-hardware/drivers/kernel/irp-mn-query-pnp-device-state">IRP_MN_QUERY_PNP_DEVICE_STATE</a> request to the device stack, to determine the current PnP state of the device.

## -see-also

[IRP_MN_QUERY_PNP_DEVICE_STATE](/windows-hardware/drivers/kernel/irp-mn-query-pnp-device-state)



[PNP_DEVICE_STATE](/windows-hardware/drivers/kernel/handling-an-irp-mn-surprise-removal-request#about-pnpdevicestate)