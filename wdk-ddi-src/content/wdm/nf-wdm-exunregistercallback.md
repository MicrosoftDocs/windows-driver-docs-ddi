---
UID: NF:wdm.ExUnregisterCallback
title: ExUnregisterCallback function
author: windows-driver-content
description: The ExUnregisterCallback routine removes a callback routine previously registered with a callback object from the list of routines to be called during the notification process.
old-location: kernel\exunregistercallback.htm
old-project: kernel
ms.assetid: a7631732-fac5-458a-b644-eaffd5e53c31
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.exunregistercallback, ExUnregisterCallback, ExUnregisterCallback routine [Kernel-Mode Driver Architecture], wdm/ExUnregisterCallback, k102_981ea9e7-42fc-4c63-9cc9-5d7aa3d35b72.xml
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
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
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
-	ExUnregisterCallback
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExUnregisterCallback function


## -description


The <b>ExUnregisterCallback</b> routine removes a callback routine previously registered with a callback object from the list of routines to be called during the notification process.


## -syntax


````
VOID ExUnregisterCallback(
  _Inout_ PVOID CbRegistration
);
````


## -parameters




### -param CallbackRegistration

TBD




#### - CbRegistration [in, out]

Specifies the callback routine to unregister. This must be the value returned by <b>ExRegisterCallback</b> when the callback was registered. 


## -returns



None




## -remarks



For more information about callback objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540718">Callback Objects</a>. 




## -see-also

<a href="..\wdm\nf-wdm-excreatecallback.md">ExCreateCallback</a>



<a href="..\wdm\nf-wdm-exregistercallback.md">ExRegisterCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExUnregisterCallback routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

