---
UID: NE:wdm._IO_CONTAINER_INFORMATION_CLASS
title: "_IO_CONTAINER_INFORMATION_CLASS"
author: windows-driver-content
description: The IO_CONTAINER_INFORMATION_CLASS enumeration contains constants that indicate the classes of system information that a kernel-mode driver can request.
old-location: kernel\io_container_information_class.htm
old-project: kernel
ms.assetid: 359ed0d2-91b1-46d1-a358-babe7cb993fb
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: IO_CONTAINER_INFORMATION_CLASS, IO_CONTAINER_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], IoMaxContainerInformationClass, IoSessionStateInformation, _IO_CONTAINER_INFORMATION_CLASS, kernel.io_container_information_class, sysenum_f1533e86-b529-4ef0-b603-e57f4863b740.xml, wdm/IO_CONTAINER_INFORMATION_CLASS, wdm/IoMaxContainerInformationClass, wdm/IoSessionStateInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	IO_CONTAINER_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: IO_CONTAINER_INFORMATION_CLASS
---

# _IO_CONTAINER_INFORMATION_CLASS enumeration


## -description


The <b>IO_CONTAINER_INFORMATION_CLASS</b> enumeration contains constants that indicate the classes of system information that a kernel-mode driver can request.


## -enum-fields




### -field IoSessionStateInformation

Session state information. A driver uses this enumeration constant to request information about a user session. 


### -field IoMaxContainerInformationClass

Specifies the maximum value in this enumeration type. 


## -remarks



To request system information, a driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549164">IoGetContainerInformation</a> routine and sets this routine's <i>InformationClass</i> parameter to an <b>IO_CONTAINER_NOTIFICATION_CLASS</b> constant (other than <b>IoMaxContainerInformationClass</b>). Currently, <b>IoGetContainerInformation</b> supports only <i>InformationClass</i> = <b>IoSessionStateInformation</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549164">IoGetContainerInformation</a>
 

 

