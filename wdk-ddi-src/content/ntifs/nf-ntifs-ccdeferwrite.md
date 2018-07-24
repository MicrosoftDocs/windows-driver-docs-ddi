---
UID: NF:ntifs.CcDeferWrite
title: CcDeferWrite function
author: windows-driver-content
description: The CcDeferWrite routine defers writing to a cached file.
old-location: ifsk\ccdeferwrite.htm
tech.root: ifsk
ms.assetid: a655bcde-c627-4c90-8579-348ab0174c27
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CcDeferWrite, CcDeferWrite routine [Installable File System Drivers], ccref_06158fb8-cf33-42fa-bf7c-94b3a5e1fcfd.xml, ifsk.ccdeferwrite, ntifs/CcDeferWrite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcDeferWrite
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcDeferWrite function


## -description


The <b>CcDeferWrite</b> routine defers writing to a cached file. The post routine that is supplied, is called by the cache manager when it can accommodate the write operation.


## -parameters




### -param FileObject [in]

Pointer to a file object for the cached file to which the data is to be written.


### -param PostRoutine [in]

Address of a routine for the cache manager to call to write to the cached file. Note that it is possible that this routine will be called immediately, even if <a href="https://msdn.microsoft.com/library/windows/hardware/ff539021">CcCanIWrite</a> has just returned <b>FALSE</b> .

The post routine is defined in ntifs.h as:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID (*PCC_POST_DEFERRED_WRITE) (
    _In_ PVOID Context1,
    _In_ PVOID Context2
    );</pre>
</td>
</tr>
</table></span></div>

### -param Context1 [in]

First parameter for the post routine at <i>PostRoutine</i>.


### -param Context2 [in]

Second parameter for the post routine at <i>PostRoutine</i>.


### -param BytesToWrite [in]

Number of bytes of data to be written.


### -param Retrying [in]

Set to <b>FALSE</b> if the request is being posted for the first time, <b>TRUE</b> otherwise.


## -returns



None




## -remarks



A file system would normally call <b>CcDeferWrite</b> after receiving a return value of <b>FALSE</b> from <a href="https://msdn.microsoft.com/library/windows/hardware/ff539021">CcCanIWrite</a>.

To cache a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.

The context parameters passed to <i>PostRoutine</i> are typically the I/O request and related context data.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539021">CcCanIWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539209">CcSetDirtyPageThreshold</a>
 

 

