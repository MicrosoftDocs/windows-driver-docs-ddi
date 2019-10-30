---
UID: NF:ntddk.RtlRunOnceComplete
title: RtlRunOnceComplete function (ntddk.h)
description: The RtlRunOnceComplete routine completes the one-time initialization began by RtlRunOnceBeginInitialize.
old-location: kernel\rtlrunoncecomplete.htm
tech.root: kernel
ms.assetid: 1cdc4fde-2370-4e58-9e67-dec731cdb935
ms.date: 04/30/2018
ms.keywords: RtlRunOnceComplete, RtlRunOnceComplete routine [Kernel-Mode Driver Architecture], k109_00290091-7130-4217-8098-0baa7309223c.xml, kernel.rtlrunoncecomplete, ntddk/RtlRunOnceComplete
ms.topic: function
f1_keywords:
 - "ntddk/RtlRunOnceComplete"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlRunOnceComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlRunOnceComplete function


## -description


The <b>RtlRunOnceComplete</b> routine completes the one-time initialization began by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrunoncebegininitialize">RtlRunOnceBeginInitialize</a>.


## -parameters




### -param RunOnce [in, out]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_RUN_ONCE</a> one-time initialization structure.


### -param Flags [in]

Drivers can optionally specify one or more of the following flags:





#### RTL_RUN_ONCE_ASYNC

Operate in asynchronous mode. This mode enables multiple completion attempts to execute in parallel. If this flag is used, subsequent calls to the <b>RtlRunOnceComplete</b> routine will fail unless this flag is also specified.



#### RTL_RUN_ONCE_INIT_FAILED

The initialization attempt failed. 


### -param Context [in, optional]

Specifies the initialized data. 


## -returns



<b>RtlRunOnceComplete</b> returns one of the following NTSTATUS values:

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
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The operation could not be completed. If the caller specified RTL_RUN_ONCE_ASYNC in the <i>Flags</i> parameter, this value can indicate that another thread completed the initialization.

</td>
</tr>
</table>
 




## -remarks



If <b>RtlRunOnceComplete</b> returns STATUS_SUCCESS, any subsequent call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrunoncebegininitialize">RtlRunOnceBeginInitialize</a> for the same <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_RUN_ONCE</a> structure supplies <i>Context</i> as the initialized data.

If the caller specified RTL_RUN_ONCE_ASYNC in the <i>Flags</i> parameter and <b>RtlRunOnceComplete</b> returns any value other than STATUS_SUCCESS, the caller must clean up any initialization that it attempted. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_RUN_ONCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrunoncebegininitialize">RtlRunOnceBeginInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrunonceexecuteonce">RtlRunOnceExecuteOnce</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrunonceinitialize">RtlRunOnceInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-rtl_run_once_init_fn">RunOnceInitialization</a>
 

 

