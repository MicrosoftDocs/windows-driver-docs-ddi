---
UID: NF:wdm.RtlLengthSecurityDescriptor
title: RtlLengthSecurityDescriptor function
author: windows-driver-content
description: The RtlLengthSecurityDescriptor routine returns the size of a given security descriptor.
old-location: kernel\rtllengthsecuritydescriptor.htm
old-project: kernel
ms.assetid: e06888eb-2ced-46c0-bdbf-3bad57020bf7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.rtllengthsecuritydescriptor, wdm/RtlLengthSecurityDescriptor, RtlLengthSecurityDescriptor, RtlLengthSecurityDescriptor routine [Kernel-Mode Driver Architecture], k109_ea245194-f36b-4b47-9d81-2d72fc19d5bc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlLengthSecurityDescriptor
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlLengthSecurityDescriptor function


## -description


The <b>RtlLengthSecurityDescriptor</b> routine returns the size of a given security descriptor.


## -syntax


````
ULONG RtlLengthSecurityDescriptor(
  _In_ PSECURITY_DESCRIPTOR SecurityDescriptor
);
````


## -parameters




### -param SecurityDescriptor [in]

Pointer to a <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>. 


## -returns



<b>RtlLengthSecurityDescriptor</b> returns the size in bytes of the descriptor. 




## -see-also

<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>



<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlLengthSecurityDescriptor routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

