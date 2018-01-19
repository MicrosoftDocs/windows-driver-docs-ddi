---
UID: NF:ntddk.RtlRunOnceBeginInitialize
title: RtlRunOnceBeginInitialize function
author: windows-driver-content
description: The RtlRunOnceBeginInitialize routine begins a one-time initialization.
old-location: kernel\rtlrunoncebegininitialize.htm
old-project: kernel
ms.assetid: ed96b2ec-95ea-47a6-a3b0-f4d018e0c8e2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlRunOnceBeginInitialize
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
req.alt-api: RtlRunOnceBeginInitialize
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlRunOnceBeginInitialize function



## -description
The <b>RtlRunOnceBeginInitialize</b> routine begins a one-time initialization.



## -syntax

````
NTSTATUS RtlRunOnceBeginInitialize(
  _Inout_ PRTL_RUN_ONCE RunOnce,
  _In_    ULONG         Flags,
  _Out_   PVOID         *Context
);
````


## -parameters

### -param RunOnce [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a> one-time initialization structure.


### -param Flags [in]

Drivers can optionally specify one or more of the following flags:




### -param RTL_RUN_ONCE_ASYNC

Perform initialization asynchronously. The driver can perform multiple completion attempts in parallel. If this flag is used, subsequent calls to this routine will fail unless this flag is also specified.


### -param RTL_RUN_ONCE_CHECK_ONLY

Do not begin initialization, but check to determine if initialization has already occurred. If <b>RtlRunOnceBeginInitialize</b> returns STATUS_SUCCESS, the initialization succeeded, and *<i>Context</i> contains the initialized data. 

</dd>
</dl>

### -param Context [out]

Specifies a pointer to a PVOID variable that receives the initialized data. The value of *<i>Context</i> is valid only when the routine returns STATUS_SUCCESS.


## -returns
<b>RtlRunOnceBeginInitialize</b> returns one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The one-time initialization has already completed. The initialized data is stored in the memory location that <i>Context</i> points to.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The caller has successfully begun one-time initialization. The caller now performs the driver-specific initialization steps and then calls <a href="..\ntddk\nf-ntddk-rtlrunoncecomplete.md">RtlRunOnceComplete</a> to complete the initialization. 

 


## -remarks
Drivers can alternatively perform one-time initialization by calling <a href="..\ntddk\nf-ntddk-rtlrunonceexecuteonce.md">RtlRunOnceExecuteOnce</a> and supplying a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563635">RunOnceInitialization</a> routine.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlrunoncecomplete.md">RtlRunOnceComplete</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlrunonceexecuteonce.md">RtlRunOnceExecuteOnce</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlrunonceinitialize.md">RtlRunOnceInitialize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563635">RunOnceInitialization</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlRunOnceBeginInitialize routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

