---
UID: NF:ntddk.RtlRunOnceInitialize
title: RtlRunOnceInitialize function
author: windows-driver-content
description: The RtlRunOnceInitialize routine initializes a RTL_RUN_ONCE structure.
old-location: kernel\rtlrunonceinitialize.htm
old-project: kernel
ms.assetid: 4d1a65af-a475-4360-9db3-d5b9e302697d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddk/RtlRunOnceInitialize, kernel.rtlrunonceinitialize, k109_7d98d21e-b6f2-4ccd-b447-0c1d612eed5b.xml, RtlRunOnceInitialize routine [Kernel-Mode Driver Architecture], RtlRunOnceInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlRunOnceInitialize
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# RtlRunOnceInitialize function


## -description


The <b>RtlRunOnceInitialize</b> routine initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a> structure.


## -syntax


````
VOID RtlRunOnceInitialize(
  _Out_ PRTL_RUN_ONCE RunOnce
);
````


## -parameters




### -param RunOnce [out]

Pointer to the <b>RTL_RUN_ONCE</b> one-time initialization structure.


## -returns



None 




## -see-also

<a href="..\ntddk\nf-ntddk-rtlrunonceexecuteonce.md">RtlRunOnceExecuteOnce</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563635">RunOnceInitialization</a>



<a href="..\ntddk\nf-ntddk-rtlrunoncecomplete.md">RtlRunOnceComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a>



<a href="..\ntddk\nf-ntddk-rtlrunoncebegininitialize.md">RtlRunOnceBeginInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlRunOnceInitialize routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

