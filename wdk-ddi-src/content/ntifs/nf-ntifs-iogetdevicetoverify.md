---
UID: NF:ntifs.IoGetDeviceToVerify
title: IoGetDeviceToVerify function
author: windows-driver-content
description: The IoGetDeviceToVerify routine returns a pointer to the device object, representing a removable-media device, that is the target of the given thread's I/O request.
old-location: ifsk\iogetdevicetoverify.htm
old-project: ifsk
ms.assetid: 3dcd33ac-845a-4519-b697-5917687a9672
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoGetDeviceToVerify, IoGetDeviceToVerify routine [Installable File System Drivers], ifsk.iogetdevicetoverify, k104_47163b80-0b35-40e0-9a30-3f5e2fe51bba.xml, ntifs/IoGetDeviceToVerify
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetDeviceToVerify
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoGetDeviceToVerify function


## -description


The <b>IoGetDeviceToVerify</b> routine returns a pointer to the device object, representing a removable-media device, that is the target of the given thread's I/O request.


## -parameters




### -param Thread [in]

Pointer to the thread for which a highest-level driver is attempting to verify the validity of the media on which the thread has opened a file.


## -returns



<b>IoGetDeviceToVerify</b> returns a pointer to the device object representing a device on which the media should be verified, or it returns <b>NULL</b>.




## -remarks



In general, highest-level drivers, particularly file systems, are most likely to call this routine.

An underlying removable-media device driver is responsible for notifying higher-level drivers, particularly the file system, when the media appears to have changed since the last access to the target device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549375">IoIsErrorUserInduced</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548529">IoSetDeviceToVerify</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549707">IoSetHardErrorOrVerifyDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a>
 

 

