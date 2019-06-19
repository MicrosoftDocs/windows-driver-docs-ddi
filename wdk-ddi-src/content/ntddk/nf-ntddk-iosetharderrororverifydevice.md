---
UID: NF:ntddk.IoSetHardErrorOrVerifyDevice
title: IoSetHardErrorOrVerifyDevice function (ntddk.h)
description: Lower-level drivers call the IoSetHardErrorOrVerifyDevice routine to identify a removable media device that has encountered an error, so that a file system driver can prompt the user to verify that the medium is valid.
old-location: kernel\iosetharderrororverifydevice.htm
tech.root: kernel
ms.assetid: 67f41d3e-d306-400b-9970-88c62f0f7a7f
ms.date: 04/30/2018
ms.keywords: IoSetHardErrorOrVerifyDevice, IoSetHardErrorOrVerifyDevice routine [Kernel-Mode Driver Architecture], k104_60c33e0c-64d3-404b-85a3-57e7da269404.xml, kernel.iosetharderrororverifydevice, ntddk/IoSetHardErrorOrVerifyDevice
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoSetHardErrorOrVerifyDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSetHardErrorOrVerifyDevice function


## -description


Lower-level drivers call the <b>IoSetHardErrorOrVerifyDevice</b> routine to identify a removable media device that has encountered an error, so that a file system driver can prompt the user to verify that the medium is valid.


## -parameters




### -param Irp [in]

Pointer to the IRP for which the driver encountered a user-induced error.


### -param DeviceObject [in]

Pointer to the target device to be verified for the I/O operation. 


## -returns



None




## -remarks



Lower-level drivers for removal media devices must call <b>IoSetHardErrorOrVerifyDevice</b> before completing an IRP, if a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549375">IoIsErrorUserInduced</a> returns <b>TRUE</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>.

Subsequently, a file system driver will use information supplied in the specified device object to send a dialog box to the user, who can correct the error and retry the operation or cancel it.

The IRP passed to <b>IoSetHardErrorOrVerifyDevice</b> must be associated with a thread. Therefore, before a driver calls <b>IoSetHardErrorOrVerifyDevice</b>, it must verify that <i>irp</i><b>->Tail.Overlay</b>.Thread is not <b>NULL</b>. If the value is <b>NULL</b>, <b>IoSetHardErrorOrVerifyDevice</b> must not be called using the current IRP. Instead, the driver should check all IRPs subsequently received and processed, until one is received for which <i>irp</i><b>->Tail.Overlay</b>.Thread is not <b>NULL</b>. At that point, <b>IoSetHardErrorOrVerifyDevice</b> can be called. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549375">IoIsErrorUserInduced</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549482">IoRaiseHardError</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549488">IoRaiseInformationalHardError</a>
 

 

