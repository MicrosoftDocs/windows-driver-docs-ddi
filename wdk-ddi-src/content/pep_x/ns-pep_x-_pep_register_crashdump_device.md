---
UID: NS:pep_x._PEP_REGISTER_CRASHDUMP_DEVICE
title: _PEP_REGISTER_CRASHDUMP_DEVICE (pep_x.h)
description: The PEP_REGISTER_CRASHDUMP_DEVICE structure provides a callback routine to turn on a crash-dump device.
old-location: kernel\pep_register_crashdump_device.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_REGISTER_CRASHDUMP_DEVICE structure"]
ms.keywords: "*PPEP_REGISTER_CRASHDUMP_DEVICE, PEP_REGISTER_CRASHDUMP_DEVICE, PEP_REGISTER_CRASHDUMP_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_REGISTER_CRASHDUMP_DEVICE, PPEP_REGISTER_CRASHDUMP_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_REGISTER_CRASHDUMP_DEVICE, kernel.pep_register_crashdump_device, pepfx/PEP_REGISTER_CRASHDUMP_DEVICE, pepfx/PPEP_REGISTER_CRASHDUMP_DEVICE"
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
req.irql: 
targetos: Windows
req.typenames: PEP_REGISTER_CRASHDUMP_DEVICE, *PPEP_REGISTER_CRASHDUMP_DEVICE
f1_keywords:
 - _PEP_REGISTER_CRASHDUMP_DEVICE
 - pep_x/_PEP_REGISTER_CRASHDUMP_DEVICE
 - PPEP_REGISTER_CRASHDUMP_DEVICE
 - pep_x/PPEP_REGISTER_CRASHDUMP_DEVICE
 - PEP_REGISTER_CRASHDUMP_DEVICE
 - pep_x/PEP_REGISTER_CRASHDUMP_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_REGISTER_CRASHDUMP_DEVICE
---

# _PEP_REGISTER_CRASHDUMP_DEVICE structure (pep_x.h)


## -description

The <b>PEP_REGISTER_CRASHDUMP_DEVICE</b> structure provides a callback routine to turn on a crash-dump device.

## -struct-fields

### -field PowerOnDumpDeviceCallback

[out] A pointer to a <a href="/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbackpoweroncrashdumpdevice">PowerOnDumpDeviceCallback</a> callback routine that is implemented by the platform extension plug-in (PEP). This routine handles requests from the Windows kernel to turn on the crash-dump device so that a crash dump can be saved. For more information, see <a href="/windows-hardware/drivers/debugger/kernel-mode-dump-files">Kernel-Mode Dump Files</a>.

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the crash-dump device. The PEP supplied this handle in response to a previous <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_CRASHDUMP_DEVICE</a> notification. The <b>DeviceHandle</b> member of the structure contains an input value that is supplied by the Windows <a href="/windows-hardware/drivers/ddi/_kernel/#device-power-management">power management framework</a> (PoFx) when this notification is sent to the PEP. The <b>PowerOnDumpDeviceCallbackmember</b> contains an output value that the PEP writes to the structure in response to the notification.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_CRASHDUMP_DEVICE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbackpoweroncrashdumpdevice">PowerOnDumpDeviceCallback</a>
