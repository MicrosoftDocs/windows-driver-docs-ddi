---
UID: NE:wdm._IO_CONTAINER_INFORMATION_CLASS
title: _IO_CONTAINER_INFORMATION_CLASS (wdm.h)
description: The IO_CONTAINER_INFORMATION_CLASS enumeration contains constants that indicate the classes of system information that a kernel-mode driver can request.
old-location: kernel\io_container_information_class.htm
tech.root: kernel
ms.assetid: 359ed0d2-91b1-46d1-a358-babe7cb993fb
ms.date: 04/30/2018
keywords: ["_IO_CONTAINER_INFORMATION_CLASS enumeration"]
ms.keywords: IO_CONTAINER_INFORMATION_CLASS, IO_CONTAINER_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], IoMaxContainerInformationClass, IoSessionStateInformation, _IO_CONTAINER_INFORMATION_CLASS, kernel.io_container_information_class, sysenum_f1533e86-b529-4ef0-b603-e57f4863b740.xml, wdm/IO_CONTAINER_INFORMATION_CLASS, wdm/IoMaxContainerInformationClass, wdm/IoSessionStateInformation
f1_keywords:
 - "wdm/IO_CONTAINER_INFORMATION_CLASS"
 - "IO_CONTAINER_INFORMATION_CLASS"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- IO_CONTAINER_INFORMATION_CLASS
product:
- Windows
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



To request system information, a driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetcontainerinformation">IoGetContainerInformation</a> routine and sets this routine's <i>InformationClass</i> parameter to an <b>IO_CONTAINER_NOTIFICATION_CLASS</b> constant (other than <b>IoMaxContainerInformationClass</b>). Currently, <b>IoGetContainerInformation</b> supports only <i>InformationClass</i> = <b>IoSessionStateInformation</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetcontainerinformation">IoGetContainerInformation</a>
 

 

