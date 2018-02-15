---
UID: NF:wdm.PoFxRegisterCrashdumpDevice
title: PoFxRegisterCrashdumpDevice function
author: windows-driver-content
description: The PoFxRegisterCrashdumpDevice routine registers a crash-dump device.
old-location: kernel\pofxregistercrashdumpdevice.htm
old-project: kernel
ms.assetid: 3237B68F-838A-4443-89FD-DC7815EAB403
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.pofxregistercrashdumpdevice, wdm/PoFxRegisterCrashdumpDevice, PoFxRegisterCrashdumpDevice, PoFxRegisterCrashdumpDevice routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ntoskrnl.lib
-	ntoskrnl.dll
apiname:
-	PoFxRegisterCrashdumpDevice
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoFxRegisterCrashdumpDevice function


## -description


The <b>PoFxRegisterCrashdumpDevice</b> routine registers a crash-dump device.


## -syntax


````
NTSTATUS PoFxRegisterCrashdumpDevice(
   POHANDLE Handle
);
````


## -parameters




### -param Handle

A handle that represents the registration of the crash-dump device with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The device driver previously received this handle from the <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> routine.


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

The driver must call <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> to register the device with PoFx before calling <b>PoFxRegisterCrashdumpDevice</b>.

The driver for a crash-dump device can call the <a href="..\wdm\nf-wdm-pofxpoweroncrashdumpdevice.md">PoFxPowerOnCrashdumpDevice</a> routine to request that the PEP turn the device on.

For more information about crash dumps, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551880">Kernel-Mode Dump Files</a>.

<b>PoFxRegisterCrashdumpDevice</b> must be called at IRQL = PASSIVE_LEVEL.




## -see-also

<a href="..\wdm\nf-wdm-pofxpoweroncrashdumpdevice.md">PoFxPowerOnCrashdumpDevice</a>



<a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoFxRegisterCrashdumpDevice routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

