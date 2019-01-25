---
UID: NF:wdm.PoFxPowerOnCrashdumpDevice
title: PoFxPowerOnCrashdumpDevice function (wdm.h)
description: The PoFxPowerOnCrashdumpDevice routine requests that a crash-dump device be turned on.
old-location: kernel\pofxpoweroncrashdumpdevice.htm
tech.root: kernel
ms.assetid: 41560DC4-EE5E-4756-8540-ACC19835A9DA
ms.date: 04/30/2018
ms.keywords: PoFxPowerOnCrashdumpDevice, PoFxPowerOnCrashdumpDevice routine [Kernel-Mode Driver Architecture], kernel.pofxpoweroncrashdumpdevice, wdm/PoFxPowerOnCrashdumpDevice
ms.topic: function
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
req.irql: "<= HIGH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ntoskrnl.lib
-	ntoskrnl.dll
api_name:
-	PoFxPowerOnCrashdumpDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoFxPowerOnCrashdumpDevice function


## -description


The <b>PoFxPowerOnCrashdumpDevice</b> routine requests that a crash-dump device be turned on.


## -parameters




### -param Handle [in]

A handle that represents the registration of the crash-dump device with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The device driver previously received this handle from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a> routine.


### -param Context [in, optional]

A pointer to a device-specific context. This pointer is passed as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186875">PowerOnDumpDeviceCallback</a> callback routine that is implemented by the platform extension plug-in (PEP) for the device. The context information is stored in a format that is defined by the device driver and is understood by the PEP. This context is opaque to the operating system. The driver can set this parameter to NULL if the PEP does not require a context.


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

For more information about crash dumps, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551880">Kernel-Mode Dump Files</a>.

This routine can be called at IRQL &lt;= HIGH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186875">PowerOnDumpDeviceCallback</a>
 

 

