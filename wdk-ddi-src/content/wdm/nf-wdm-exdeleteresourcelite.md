---
UID: NF:wdm.ExDeleteResourceLite
title: ExDeleteResourceLite function
author: windows-driver-content
description: The ExDeleteResourceLite routine deletes a given resource from the system's resource list.
old-location: kernel\exdeleteresourcelite.htm
old-project: kernel
ms.assetid: 83efb1eb-4c45-4bfc-84dd-88032e40076a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExDeleteResourceLite routine [Kernel-Mode Driver Architecture], ExDeleteResourceLite, wdm/ExDeleteResourceLite, k102_92907ac3-1391-4ede-8ffa-71a211c7634e.xml, kernel.exdeleteresourcelite
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExDeleteResourceLite
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExDeleteResourceLite function


## -description


The <b>ExDeleteResourceLite</b> routine deletes a given resource from the system's resource list.


## -syntax


````
NTSTATUS ExDeleteResourceLite(
  _Inout_ PERESOURCE Resource
);
````


## -parameters




### -param Resource [in, out]

A pointer to the caller-supplied storage for the initialized resource variable to be deleted.


## -returns


<b>ExDeleteResourceLite</b> returns STATUS_SUCCESS if the resource was deleted.



## -remarks


After calling <b>ExDeleteResourceLite</b>, the caller can free the memory it allocated for its resource.



## -see-also

<a href="..\wdm\nf-wdm-exinitializeresourcelite.md">ExInitializeResourceLite</a>

<a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>

<a href="..\wdm\nf-wdm-exreinitializeresourcelite.md">ExReinitializeResourceLite</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExDeleteResourceLite routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

