---
UID: NE:wdm._IO_CONTAINER_INFORMATION_CLASS
title: "_IO_CONTAINER_INFORMATION_CLASS"
author: windows-driver-content
description: The IO_CONTAINER_INFORMATION_CLASS enumeration contains constants that indicate the classes of system information that a kernel-mode driver can request.
old-location: kernel\io_container_information_class.htm
old-project: kernel
ms.assetid: 359ed0d2-91b1-46d1-a358-babe7cb993fb
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, A, C, E, F, I, IO_CONTAINER_INFORMATION_CLASS, IO_CONTAINER_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], IoMaxContainerInformationClass, IoSessionStateInformation, L, M, N, O, R, S, T, _, _IO_CONTAINER_INFORMATION_CLASS, kernel.io_container_information_class, sysenum_f1533e86-b529-4ef0-b603-e57f4863b740.xml, wdm/IO_CONTAINER_INFORMATION_CLASS, wdm/IoMaxContainerInformationClass, wdm/IoSessionStateInformation"
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	IO_CONTAINER_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: IO_CONTAINER_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _IO_CONTAINER_INFORMATION_CLASS enumeration


## -description


The <b>IO_CONTAINER_INFORMATION_CLASS</b> enumeration contains constants that indicate the classes of system information that a kernel-mode driver can request.


## -syntax


````
typedef enum _IO_CONTAINER_INFORMATION_CLASS { 
  IoSessionStateInformation       = 0,
  IoMaxContainerInformationClass  = 1
} IO_CONTAINER_INFORMATION_CLASS;
````


## -enum-fields




### -field IoSessionStateInformation

Session state information. A driver uses this enumeration constant to request information about a user session. 


### -field IoMaxContainerInformationClass

Specifies the maximum value in this enumeration type. 


## -remarks



To request system information, a driver calls the <a href="..\wdm\nf-wdm-iogetcontainerinformation.md">IoGetContainerInformation</a> routine and sets this routine's <i>InformationClass</i> parameter to an <b>IO_CONTAINER_NOTIFICATION_CLASS</b> constant (other than <b>IoMaxContainerInformationClass</b>). Currently, <b>IoGetContainerInformation</b> supports only <i>InformationClass</i> = <b>IoSessionStateInformation</b>. 




## -see-also

<a href="..\wdm\nf-wdm-iogetcontainerinformation.md">IoGetContainerInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_CONTAINER_INFORMATION_CLASS enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

