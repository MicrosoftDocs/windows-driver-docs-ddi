---
UID: NC:pep_x.PEPCALLBACKPOWERONCRASHDUMPDEVICE
title: PEPCALLBACKPOWERONCRASHDUMPDEVICE (pep_x.h)
description: The PowerOnDumpDeviceCallback callback routine turns on the crash-dump device.
old-location: kernel\powerondumpdevicecallback.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEPCALLBACKPOWERONCRASHDUMPDEVICE callback function"]
ms.keywords: PEPCALLBACKPOWERONCRASHDUMPDEVICE, PowerOnDumpDeviceCallback, PowerOnDumpDeviceCallback routine [Kernel-Mode Driver Architecture], kernel.powerondumpdevicecallback, pepfx/PowerOnDumpDeviceCallback
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.lib: 
req.dll: 
req.irql: Called at HIGH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - PEPCALLBACKPOWERONCRASHDUMPDEVICE
 - pep_x/PEPCALLBACKPOWERONCRASHDUMPDEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - pepfx.h
api_name:
 - PowerOnDumpDeviceCallback
---

# PEPCALLBACKPOWERONCRASHDUMPDEVICE callback function (pep_x.h)


## -description

The <i>PowerOnDumpDeviceCallback</i> callback routine turns on the crash-dump device.

## -parameters

### -param CrashdumpInformation 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_crashdump_information">PEP_CRASHDUMP_INFORMATION</a> structure that contains information about the crash-dump device.

## -returns

This routine returns TRUE if it succeeds in turning on power to the crash-dump device. Otherwise, it returns FALSE.

## -remarks

This routine is implemented by the platform extension plug-in (PEP). The routine handles requests from the Windows kernel to turn on the crash-dump device so that a crash dump can be saved to disk.

The PEP registers its <i>PowerOnDumpDeviceCallback</i> routine in response to a <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_CRASHDUMP_DEVICE</a> notification from the Windows <a href="/windows-hardware/drivers/ddi/_kernel/#device-power-management">power management framework</a> (PoFx).

The <i>PowerOnDumpDeviceCallback</i> routine is called at IRQL = HIGH_LEVEL with interrupts disabled. Thus, this routine cannot use timers, events, or any synchronization primitives other than spin locks.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_crashdump_information">PEP_CRASHDUMP_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_CRASHDUMP_DEVICE</a>
