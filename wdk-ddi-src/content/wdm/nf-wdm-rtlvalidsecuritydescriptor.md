---
UID: NF:wdm.RtlValidSecurityDescriptor
title: RtlValidSecurityDescriptor function
author: windows-driver-content
description: The RtlValidSecurityDescriptor routine checks a given security descriptor's validity.
old-location: kernel\rtlvalidsecuritydescriptor.htm
old-project: kernel
ms.assetid: 50d07154-a6d2-4b95-822f-33c0f37ece2f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k109_59b52650-028b-4e7a-8a00-234f40e354f2.xml, kernel.rtlvalidsecuritydescriptor, wdm/RtlValidSecurityDescriptor, RtlValidSecurityDescriptor routine [Kernel-Mode Driver Architecture], RtlValidSecurityDescriptor
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	RtlValidSecurityDescriptor
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlValidSecurityDescriptor function


## -description


The <b>RtlValidSecurityDescriptor</b> routine checks a given security descriptor's validity.


## -syntax


````
BOOLEAN RtlValidSecurityDescriptor(
  _In_ PSECURITY_DESCRIPTOR SecurityDescriptor
);
````


## -parameters




### -param SecurityDescriptor [in]

Pointer to the <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> to be checked.


## -returns


<b>RtlValidSecurityDescriptor</b> returns <b>TRUE</b> if the given descriptor is valid.



## -remarks


The routine checks the validity of an absolute-format security descriptor. To check the validity of a self-relative security descriptor, use the <a href="..\wdm\nf-wdm-rtlvalidrelativesecuritydescriptor.md">RtlValidRelativeSecurityDescriptor</a> routine instead.



## -see-also

<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>

<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>

<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>

<a href="..\wdm\nf-wdm-rtlvalidrelativesecuritydescriptor.md">RtlValidRelativeSecurityDescriptor</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlValidSecurityDescriptor routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

