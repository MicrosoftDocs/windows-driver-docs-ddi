---
UID: NF:wdm.RtlValidSecurityDescriptor
title: RtlValidSecurityDescriptor function
author: windows-driver-content
description: The RtlValidSecurityDescriptor routine checks a given security descriptor's validity.
old-location: kernel\rtlvalidsecuritydescriptor.htm
old-project: kernel
ms.assetid: 50d07154-a6d2-4b95-822f-33c0f37ece2f
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlValidSecurityDescriptor, RtlValidSecurityDescriptor routine [Kernel-Mode Driver Architecture], k109_59b52650-028b-4e7a-8a00-234f40e354f2.xml, kernel.rtlvalidsecuritydescriptor, wdm/RtlValidSecurityDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlValidSecurityDescriptor
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlValidSecurityDescriptor function


## -description


The <b>RtlValidSecurityDescriptor</b> routine checks a given security descriptor's validity.


## -parameters




### -param SecurityDescriptor [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> to be checked.


## -returns



<b>RtlValidSecurityDescriptor</b> returns <b>TRUE</b> if the given descriptor is valid.




## -remarks



The routine checks the validity of an absolute-format security descriptor. To check the validity of a self-relative security descriptor, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563019">RtlValidRelativeSecurityDescriptor</a> routine instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561827">RtlCreateSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562025">RtlLengthSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562781">RtlSetDaclSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563019">RtlValidRelativeSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>
 

 

