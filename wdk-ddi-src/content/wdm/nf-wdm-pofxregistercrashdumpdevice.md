---
UID: NF:wdm.PoFxRegisterCrashdumpDevice
title: PoFxRegisterCrashdumpDevice function (wdm.h)
description: The PoFxRegisterCrashdumpDevice routine registers a crash-dump device.
old-location: kernel\pofxregistercrashdumpdevice.htm
tech.root: kernel
ms.assetid: 3237B68F-838A-4443-89FD-DC7815EAB403
ms.date: 04/30/2018
keywords: ["PoFxRegisterCrashdumpDevice function"]
ms.keywords: PoFxRegisterCrashdumpDevice, PoFxRegisterCrashdumpDevice routine [Kernel-Mode Driver Architecture], kernel.pofxregistercrashdumpdevice, wdm/PoFxRegisterCrashdumpDevice
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PoFxRegisterCrashdumpDevice
 - wdm/PoFxRegisterCrashdumpDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ntoskrnl.lib
 - ntoskrnl.dll
api_name:
 - PoFxRegisterCrashdumpDevice
---

# PoFxRegisterCrashdumpDevice function


## -description

The <b>PoFxRegisterCrashdumpDevice</b> routine registers a crash-dump device.

## -parameters

### -param Handle

A handle that represents the registration of the crash-dump device with the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx). The device driver previously received this handle from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine.

## -returns

<b>PoFxRegisterCrashdumpDevice</b> returns STATUS_SUCCESS if the routine successfully registers the crash-dump device. Possible error return values include the following status codes.

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
There is no PEP for this device.

</td>
</tr>
</table>

## -remarks

This routine is called by the driver for a crash-dump device to inform PoFx that the device is part of the crash-dump device chain. Several devices (storage controller, PCI controller, and so on) might need to be turned on so that the Windows kernel can write a crash-dump file to disk. When a fatal system error occurs, the kernel tries to turn on the crash-dump devices and save the crash-dump file.

The driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> to register the device with PoFx before calling <b>PoFxRegisterCrashdumpDevice</b>.

The driver for a crash-dump device can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxpoweroncrashdumpdevice">PoFxPowerOnCrashdumpDevice</a> routine to request that the PEP turn the device on.

For more information about crash dumps, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/kernel-mode-dump-files">Kernel-Mode Dump Files</a>.

<b>PoFxRegisterCrashdumpDevice</b> must be called at IRQL = PASSIVE_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxpoweroncrashdumpdevice">PoFxPowerOnCrashdumpDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>

