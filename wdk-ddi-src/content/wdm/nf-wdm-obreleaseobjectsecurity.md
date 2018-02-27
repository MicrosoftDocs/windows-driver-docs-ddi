---
UID: NF:wdm.ObReleaseObjectSecurity
title: ObReleaseObjectSecurity function
author: windows-driver-content
description: The ObReleaseObjectSecurity routine is the reciprocal to ObGetObjectSecurity.
old-location: kernel\obreleaseobjectsecurity.htm
old-project: kernel
ms.assetid: d4f9d02a-2541-445a-95f1-e08ebb0c8a39
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ObReleaseObjectSecurity, ObReleaseObjectSecurity routine [Kernel-Mode Driver Architecture], k107_b43166d5-3dac-420a-803e-053b272d3405.xml, kernel.obreleaseobjectsecurity, wdm/ObReleaseObjectSecurity
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
req.ddi-compliance: IrqlApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ObReleaseObjectSecurity
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ObReleaseObjectSecurity function


## -description


The <b>ObReleaseObjectSecurity</b> routine is the reciprocal to <b>ObGetObjectSecurity</b>. 


## -syntax


````
VOID ObReleaseObjectSecurity(
  _In_ PSECURITY_DESCRIPTOR SecurityDescriptor,
  _In_ BOOLEAN              MemoryAllocated
);
````


## -parameters




### -param SecurityDescriptor [in]

Pointer to the buffered <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> to be released. The caller obtained this parameter from <b>ObGetObjectSecurity</b>


### -param MemoryAllocated [in]

Specifies the value also obtained from <b>ObGetObjectSecurity</b>. 


## -returns



None




## -remarks



After a successful call to <a href="..\wdm\nf-wdm-obgetobjectsecurity.md">ObGetObjectSecurity</a>, a driver must call <b>ObReleaseObjectSecurity</b> eventually. 

<b>ObReleaseObjectSecurity</b> releases any resources that were allocated by <b>ObGetObjectSecurity</b>. It also decrements the reference count on the given security descriptor. 




## -see-also

<a href="..\wdm\nf-wdm-obgetobjectsecurity.md">ObGetObjectSecurity</a>



<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObReleaseObjectSecurity routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

