---
UID: NF:wdm.ObReleaseObjectSecurity
title: ObReleaseObjectSecurity function
author: windows-driver-content
description: The ObReleaseObjectSecurity routine is the reciprocal to ObGetObjectSecurity.
old-location: kernel\obreleaseobjectsecurity.htm
old-project: kernel
ms.assetid: d4f9d02a-2541-445a-95f1-e08ebb0c8a39
ms.author: windowsdriverdev
ms.date: 3/1/2018
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
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



 

 


