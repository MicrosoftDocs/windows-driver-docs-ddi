---
UID: NF:ntddk.KeLeaveCriticalRegion
title: KeLeaveCriticalRegion function
author: windows-driver-content
description: The KeLeaveCriticalRegion routine reenables the delivery of normal kernel-mode APCs that were disabled by a preceding call to KeEnterCriticalRegion.
old-location: kernel\keleavecriticalregion.htm
old-project: kernel
ms.assetid: d3e90c3b-5ead-40d1-9143-a2b1fc8c255d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeLeaveCriticalRegion routine [Kernel-Mode Driver Architecture], KeLeaveCriticalRegion, wdm/KeLeaveCriticalRegion, k105_f9344044-a57f-4ee4-800c-a03edcc27196.xml, kernel.keleavecriticalregion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CriticalRegions, IrqlKeApcLte2, WithinCriticalRegion, HwStorPortProhibitedDDIs, WithinCriticalRegion(storport)
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
-	KeLeaveCriticalRegion
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# KeLeaveCriticalRegion function


## -description


The <b>KeLeaveCriticalRegion</b> routine reenables the delivery of normal kernel-mode APCs that were disabled by a preceding call to <b>KeEnterCriticalRegion</b>. 


## -syntax


````
VOID KeLeaveCriticalRegion(void);
````


## -parameters






## -returns



None




## -remarks



Highest-level drivers can call this routine while running in the context of the thread that requested the current I/O operation. 




## -see-also

<a href="..\wdm\nf-wdm-keentercriticalregion.md">KeEnterCriticalRegion</a>



<a href="..\wdm\nf-wdm-keareapcsdisabled.md">KeAreApcsDisabled</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeLeaveCriticalRegion routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

