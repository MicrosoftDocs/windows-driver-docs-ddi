---
UID: NF:wdm.ExConvertExclusiveToSharedLite
title: ExConvertExclusiveToSharedLite function
author: windows-driver-content
description: The ExConvertExclusiveToSharedLite routine converts a given resource from acquired for exclusive access to acquired for shared access.
old-location: kernel\exconvertexclusivetosharedlite.htm
old-project: kernel
ms.assetid: 140de330-7e6d-4f23-96cb-ea1228c8036c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ExConvertExclusiveToSharedLite, ExConvertExclusiveToSharedLite routine [Kernel-Mode Driver Architecture], k102_3c58f8e7-3da6-413d-9662-89a29928a6c1.xml, kernel.exconvertexclusivetosharedlite, wdm/ExConvertExclusiveToSharedLite
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
req.ddi-compliance: IrqlExApcLte3, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExConvertExclusiveToSharedLite
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExConvertExclusiveToSharedLite function


## -description


The <b>ExConvertExclusiveToSharedLite</b> routine converts a given resource from acquired for exclusive access to acquired for shared access.


## -syntax


````
VOID ExConvertExclusiveToSharedLite(
  _Inout_ PERESOURCE Resource
);
````


## -parameters




### -param Resource [in, out]

A pointer to the resource for which the access should be converted.


## -returns



None




## -remarks



The caller must have exclusive access to the given resource. During this conversion, the current thread and any other threads waiting for shared access to the resource are given shared access.




## -see-also

<a href="..\wdm\nf-wdm-exisresourceacquiredexclusivelite.md">ExIsResourceAcquiredExclusiveLite</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExConvertExclusiveToSharedLite routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

