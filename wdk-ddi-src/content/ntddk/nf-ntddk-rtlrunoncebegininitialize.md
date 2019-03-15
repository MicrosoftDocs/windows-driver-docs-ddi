---
UID: NF:ntddk.RtlRunOnceBeginInitialize
title: RtlRunOnceBeginInitialize function (ntddk.h)
description: The RtlRunOnceBeginInitialize routine begins a one-time initialization.
old-location: kernel\rtlrunoncebegininitialize.htm
tech.root: kernel
ms.assetid: ed96b2ec-95ea-47a6-a3b0-f4d018e0c8e2
ms.date: 04/30/2018
ms.keywords: RtlRunOnceBeginInitialize, RtlRunOnceBeginInitialize routine [Kernel-Mode Driver Architecture], k109_f7299ad8-4567-4ad8-a13c-2329a12af6ea.xml, kernel.rtlrunoncebegininitialize, ntddk/RtlRunOnceBeginInitialize
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlRunOnceBeginInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlRunOnceBeginInitialize function


## -description


The <b>RtlRunOnceBeginInitialize</b> routine begins a one-time initialization.


## -parameters




### -param RunOnce [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a> one-time initialization structure.


### -param Flags [in]

Drivers can optionally specify one or more of the following flags:





#### RTL_RUN_ONCE_ASYNC

Perform initialization asynchronously. The driver can perform multiple completion attempts in parallel. If this flag is used, subsequent calls to this routine will fail unless this flag is also specified.



#### RTL_RUN_ONCE_CHECK_ONLY

Do not begin initialization, but check to determine if initialization has already occurred. If <b>RtlRunOnceBeginInitialize</b> returns STATUS_SUCCESS, the initialization succeeded, and *<i>Context</i> contains the initialized data. 


### -param Context [out]

Specifies a pointer to a PVOID variable that receives the initialized data. The value of *<i>Context</i> is valid only when the routine returns STATUS_SUCCESS.


## -returns



<b>RtlRunOnceBeginInitialize</b> returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The one-time initialization has already completed. The initialized data is stored in the memory location that <i>Context</i> points to.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The caller has successfully begun one-time initialization. The caller now performs the driver-specific initialization steps and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff562763">RtlRunOnceComplete</a> to complete the initialization. 

</td>
</tr>
</table>
 




## -remarks



Drivers can alternatively perform one-time initialization by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff562765">RtlRunOnceExecuteOnce</a> and supplying a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563635">RunOnceInitialization</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562763">RtlRunOnceComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562765">RtlRunOnceExecuteOnce</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562767">RtlRunOnceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563635">RunOnceInitialization</a>
 

 

