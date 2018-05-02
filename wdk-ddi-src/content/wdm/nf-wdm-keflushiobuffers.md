---
UID: NF:wdm.KeFlushIoBuffers
title: KeFlushIoBuffers function
author: windows-driver-content
description: The KeFlushIoBuffers routine flushes the memory region described by an MDL from caches of all processors.
old-location: kernel\keflushiobuffers.htm
old-project: kernel
ms.assetid: 76954a20-7cd7-454b-a965-8c3f0cdb6e8f
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeFlushIoBuffers, KeFlushIoBuffers routine [Kernel-Mode Driver Architecture], k105_265e110c-5dad-444c-a97d-6693d7996c51.xml, kernel.keflushiobuffers, wdm/KeFlushIoBuffers
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
req.ddi-compliance: MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedReadA, MdlAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeFlushIoBuffers
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeFlushIoBuffers function


## -description


The <b>KeFlushIoBuffers</b> routine flushes the memory region described by an MDL from caches of all processors.


## -parameters




### -param Mdl [in]

A pointer to an MDL that describes the range for the I/O buffer.


### -param ReadOperation [in]

Specifies <b>TRUE</b> if the flush is being performed for a read operation, and <b>FALSE</b> for a write operation. For more information, see the following Remarks section.


### -param DmaOperation [in]

Specifies <b>TRUE</b> for a DMA transfer, <b>FALSE</b> for PIO.


## -returns



None




## -remarks



Drivers call <b>KeFlushIoBuffers</b> to maintain data integrity during DMA or PIO device transfer operations. Calling this routine affects all processors in the machine.

If <i>ReadOperation</i> is <b>TRUE</b>, the driver is reading information from the device to system memory, so valid data still might be in the processor instruction and data caches. <b>KeFlushIoBuffers</b> flushes data from all processors' caches to system memory, including the processor on which the caller is running.

If <i>ReadOperation</i> is <b>FALSE</b>, the driver is writing data from system memory to a device, so valid data might be in the processor's data cache but not yet transferred to the device. <b>KeFlushIoBuffers</b> flushes all processors' data caches, including that of the processor on which the caller is running.

As a general rule, drivers should call <b>KeFlushIoBuffers</b> just before beginning a DMA transfer operation or immediately following any PIO read operation.

<b>KeFlushIoBuffers</b> flushes only the memory region that is described by the MDL that the <i>Mdl</i> parameter points to. To flush all the memory regions that are described by an MDL chain requires a separate <b>KeFlushIoBuffers</b> call for each MDL in the chain.

For more information, see the following topics:

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545924">Flushing Cached Data during DMA Operations</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546503">Flushing Cached Data during PIO Operations</a>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>
 

 

