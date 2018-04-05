---
UID: NF:fltkernel.FltAllocateCallbackDataEx
title: FltAllocateCallbackDataEx function
author: windows-driver-content
description: The FltAllocateCallbackDataEx routine allocates a callback data structure and can preallocate memory for additional structures that a minifilter driver can use to initiate an I/O request.
old-location: ifsk\fltallocatecallbackdataex.htm
old-project: ifsk
ms.assetid: f03851a4-e1e9-4fee-b264-c2f91c6e8180
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltAllocateCallbackDataEx, FltAllocateCallbackDataEx routine [Installable File System Drivers], FltApiRef_a_to_d_9ef78123-712f-465a-8c8a-efc3d64b7001.xml, fltkernel/FltAllocateCallbackDataEx, ifsk.fltallocatecallbackdataex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltAllocateCallbackDataEx
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltAllocateCallbackDataEx function


## -description


The <b>FltAllocateCallbackDataEx</b> routine allocates a callback data structure and can preallocate memory for additional structures that a minifilter driver can use to initiate an I/O request.


## -parameters




### -param Instance [in]

An opaque instance pointer to the minifilter driver instance that is initiating the I/O operation. This parameter is required and cannot be <b>NULL</b>.


### -param FileObject [in, optional]

A pointer to a file object to be used in the I/O operation. This parameter is optional and can be <b>NULL</b>.


### -param Flags [in]

A value of zero or the following flag:

        FLT_ALLOCATE_CALLBACK_DATA_PREALLOCATE_ALL_MEMORY

If this flag is set, the routine preallocates all the memory needed by the filter manager for additional structures to be used in an I/O request.


### -param RetNewCallbackData [out]

A pointer to a caller-allocated variable that receives the address of the newly allocated callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure.


## -returns



The <b>FltAllocateCallbackDataEx</b> routine returns STATUS_SUCCESS on success or STATUS_INSUFFICIENT_RESOURCES if the routine encountered a pool allocation failure when attempting to allocate the callback data structure or if the FLT_ALLOCATE_CALLBACK_DATA_PREALLOCATE_ALL_MEMORY flag is set and additional memory could not be allocated.




## -remarks



If the FLT_ALLOCATE_CALLBACK_DATA_PREALLOCATE_ALL_MEMORY flag is set, the routine allocates all the memory needed for additional filter manager structures to be used in a subsequent I/O request. Using this flag enables a minifilter to preallocate one or more callback data structures to be used for issuing I/O requests under low memory conditions or in situations where recovering from a memory allocation failure might be complicated. 

<div class="alert"><b>Note</b>   The additional allocated memory is for use by the filter manager. The file system or other filters can still fail the I/O request due to an out-of-memory condition.</div>
<div> </div>
Set <i>FileObject</i> to <b>NULL</b> if this is a CREATE operation.

<div class="alert"><b>Important</b>    The comments for <a href="https://msdn.microsoft.com/library/windows/hardware/ff541703">FltAllocateCallbackData</a> apply to <b>FltAllocateCallbackDataEx</b> as well. Review that information in order to select the correct routine for your design. </div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541703">FltAllocateCallbackData</a>
 

 

