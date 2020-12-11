---
UID: NF:wdm.PoFxPowerOnCrashdumpDevice
title: PoFxPowerOnCrashdumpDevice function (wdm.h)
description: The PoFxPowerOnCrashdumpDevice routine requests that a crash-dump device be turned on.
old-location: kernel\pofxpoweroncrashdumpdevice.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PoFxPowerOnCrashdumpDevice function"]
ms.keywords: PoFxPowerOnCrashdumpDevice, PoFxPowerOnCrashdumpDevice routine [Kernel-Mode Driver Architecture], kernel.pofxpoweroncrashdumpdevice, wdm/PoFxPowerOnCrashdumpDevice
req.header: wdm.h
req.include-header: Pepfx.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: <= HIGH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PoFxPowerOnCrashdumpDevice
 - wdm/PoFxPowerOnCrashdumpDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ntoskrnl.lib
 - ntoskrnl.dll
api_name:
 - PoFxPowerOnCrashdumpDevice
---

# PoFxPowerOnCrashdumpDevice function


## -description

The <b>PoFxPowerOnCrashdumpDevice</b> routine requests that a crash-dump device be turned on.

## -parameters

### -param Handle 

[in]
A handle that represents the registration of the crash-dump device with the Windows <a href="/windows-hardware/drivers/ddi/_kernel/#device-power-management">power management framework</a> (PoFx). The device driver previously received this handle from the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine.

### -param Context 

[in, optional]
A pointer to a device-specific context. This pointer is passed as an input parameter to the <a href="/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbackpoweroncrashdumpdevice">PowerOnDumpDeviceCallback</a> callback routine that is implemented by the platform extension plug-in (PEP) for the device. The context information is stored in a format that is defined by the device driver and is understood by the PEP. This context is opaque to the operating system. The driver can set this parameter to NULL if the PEP does not require a context.

## -returns

<b>PoFxPowerOnCrashdumpDevice</b> returns STATUS_SUCCESS if the routine succeeds in turning on power to the device. Possible error return values include the following status codes.

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>
</td>
<td width="60%">
Not a valid handle value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_UNSUCCESSFUL</dt>
</dl>
</td>
<td width="60%">
The PEP for this device does not implement a <i>PowerOnDumpDeviceCallback</i> callback routine; or the PEP failed to turn on the device.

</td>
</tr>
</table>

## -remarks

The driver for a crash-dump device calls this routine to request that the platform extension plug-in (PEP) turn the device on so that a crash dump can be saved. All devices in the crash-dump device chain (which might include a storage controller, a PCI controller, and so on) must be turned on before a crash-dump file can be written to disk.

For more information about crash dumps, see <a href="/windows-hardware/drivers/debugger/kernel-mode-dump-files">Kernel-Mode Dump Files</a>.

This routine can be called at IRQL <= HIGH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>



<a href="/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbackpoweroncrashdumpdevice">PowerOnDumpDeviceCallback</a>
