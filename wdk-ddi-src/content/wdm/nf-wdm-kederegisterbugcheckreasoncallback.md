---
UID: NF:wdm.KeDeregisterBugCheckReasonCallback
title: KeDeregisterBugCheckReasonCallback function
author: windows-driver-content
description: The KeDeregisterBugCheckReasonCallback routine removes a callback routine that was registered by KeRegisterBugCheckReasonCallback.
old-location: kernel\kederegisterbugcheckreasoncallback.htm
old-project: kernel
ms.assetid: 3a2a8940-afe2-48f5-bcf0-abd6413eeb85
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeDeregisterBugCheckReasonCallback, KeDeregisterBugCheckReasonCallback routine [Kernel-Mode Driver Architecture], k105_f767309b-2c8a-4460-a43f-06aec0f7d401.xml, kernel.kederegisterbugcheckreasoncallback, wdm/KeDeregisterBugCheckReasonCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP Service Pack 1 (SP1), Windows Server 2003, and later versions of Windows.
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeDeregisterBugCheckReasonCallback
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeDeregisterBugCheckReasonCallback function


## -description


The <b>KeDeregisterBugCheckReasonCallback</b> routine removes a callback routine that was registered by <a href="..\wdm\nf-wdm-keregisterbugcheckreasoncallback.md">KeRegisterBugCheckReasonCallback</a>.


## -syntax


````
BOOLEAN KeDeregisterBugCheckReasonCallback(
  _Inout_ PKBUGCHECK_REASON_CALLBACK_RECORD CallbackRecord
);
````


## -parameters




### -param CallbackRecord [in, out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a> structure. <i>CallbackRecord</i> must be the same value that was passed to <a href="..\wdm\nf-wdm-keregisterbugcheckreasoncallback.md">KeRegisterBugCheckReasonCallback</a> when the callback was registered.


## -returns



<b>KeDeregisterBugCheckReasonCallback</b> returns <b>TRUE</b> if the callback is successfully removed. It returns <b>FALSE</b> if the specified callback is not registered.




## -see-also

<a href="..\wdm\nf-wdm-keregisterbugcheckreasoncallback.md">KeRegisterBugCheckReasonCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeDeregisterBugCheckReasonCallback routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

