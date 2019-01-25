---
UID: NF:wdm.KeDeregisterBugCheckCallback
title: KeDeregisterBugCheckCallback function (wdm.h)
description: The KeDeregisterBugCheckCallback routine removes a callback routine that was registered by KeRegisterBugCheckCallback.
old-location: kernel\kederegisterbugcheckcallback.htm
tech.root: kernel
ms.assetid: 0be95cee-c648-4905-9f4a-ea4e5fc794ed
ms.date: 04/30/2018
ms.keywords: KeDeregisterBugCheckCallback, KeDeregisterBugCheckCallback routine [Kernel-Mode Driver Architecture], k105_6bb11ae2-ceb1-4640-b59c-47b42496b819.xml, kernel.kederegisterbugcheckcallback, wdm/KeDeregisterBugCheckCallback
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeDeregisterBugCheckCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeDeregisterBugCheckCallback function


## -description


The <b>KeDeregisterBugCheckCallback</b> routine removes a callback routine that was registered by <a href="https://msdn.microsoft.com/library/windows/hardware/ff553105">KeRegisterBugCheckCallback</a>.


## -parameters




### -param CallbackRecord [in, out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551853">KBUGCHECK_CALLBACK_RECORD</a> structure. <i>CallbackRecord</i> must be the same value that was passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff553105">KeRegisterBugCheckCallback</a> when the callback was registered.


## -returns



<b>KeDeregisterBugCheckCallback</b> returns <b>TRUE</b> if the specified callback is successfully removed. It returns <b>FALSE</b> if the specified callback is not registered.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553105">KeRegisterBugCheckCallback</a>
 

 

