---
UID: NS:wdm._CLS_INFORMATION
title: "_CLS_INFORMATION"
description: The CLFS_INFORMATION structure holds metadata and state information for a Common Log File System (CLFS) stream and/or its underlying physical log.
old-location: kernel\clfs_information.htm
tech.root: kernel
ms.assetid: 7fe392d1-75e4-43b1-a09b-6f47981bef7e
ms.date: 04/30/2018
ms.keywords: "*PCLFS_INFORMATION, *PCLS_INFORMATION, *PPCLS_INFORMATION, CLFS_INFORMATION, CLFS_INFORMATION structure [Kernel-Mode Driver Architecture], CLS_INFORMATION, CLS_INFORMATION structure [Kernel-Mode Driver Architecture], PCLFS_INFORMATION, PCLFS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PCLS_INFORMATION, PCLS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PPCLFS_INFORMATION, PPCLFS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PPCLS_INFORMATION, PPCLS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _CLS_INFORMATION, kernel.clfs_information, kstruct_a_6935868e-7d3d-458e-a556-0c92ed99bdbf.xml, wdm/CLFS_INFORMATION, wdm/CLS_INFORMATION, wdm/PCLFS_INFORMATION, wdm/PCLS_INFORMATION, wdm/PPCLFS_INFORMATION, wdm/PPCLS_INFORMATION"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	CLS_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: CLS_INFORMATION, *PCLS_INFORMATION, *PPCLS_INFORMATION
---

# _CLS_INFORMATION structure


## -description


The <b>CLFS_INFORMATION</b> structure holds metadata and state information for a Common Log File System (CLFS) stream and/or its underlying physical log.


## -struct-fields




### -field TotalAvailable

The total available space allocated to the log. This is calculated as the sum of the sizes of all containers in the log. 


### -field CurrentAvailable

The amount of space available in the log for new records and reservation allocations. This space is the total available space minus the undo commitment space and space used for storing owner pages in a multiplexed log.


### -field TotalReservation

The amount of space reserved in the stream (or physical log) for undo operations.


### -field BaseFileSize

The size, in bytes, of the base log file.


### -field ContainerSize

The size, in bytes, of an individual container in the log. Note that all containers in the log are the same size.


### -field TotalContainers

The number of containers in the log.


### -field FreeContainers

The number of containers in the log that are not active. 


### -field TotalClients

The number of streams that share the log. 


### -field Attributes

A set of flags that specify stream (or physical log) attributes. See the <i>fFlagsAndAttributes</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a> function.


### -field FlushThreshold

The number of bytes of data (including headers) that are allowed to remain pending on the internal flush queue before CLFS automatically schedules a thread to write the flush queue to stable storage. 


### -field SectorSize

The sector size, in bytes, of the underlying disk geometry. The sector size is assumed to be a multiple of 512 and consistent across containers.


### -field MinArchiveTailLsn

The LSN of the oldest record in the log for which archiving has not taken place. The minimum of this and the base LSN determines the last container that can be reused when containers are recycled.


### -field BaseLsn

The LSN of the oldest record in the stream (or physical log) that is still needed by the stream (or log) clients.


### -field LastFlushedLsn

The LSN of the last record that was flushed to stable storage.


### -field LastLsn

The LSN of the youngest record in the stream (or physical log) that is still needed by the stream (or log) clients. 


### -field RestartLsn

The LSN of the last restart record written to the stream (or physical log). If there are no restart records, this member is equal to CLFS_LSN_INVALID.


### -field Identity

A GUID that serves as a unique identifier for the log.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff541679">ClfsQueryLogFileInformation</a> function returns information about a CLFS stream and/or its underlying physical log. The type of information returned depends on the <i>eInformationClass</i> parameter. 

If the <i>eInformationClass</i> parameter is equal to <b>ClfsLogBasicInformationPhysical</b>, <b>ClfsQueryLogFileInformation</b> returns information in a <b>CLFS_INFORMATION</b> structure, and every structure member holds a piece of information about a physical CLFS log. Even if the log is multiplexed (that is, it has several streams), all structure members hold information about the underlying physical log rather than information about one of the streams.

If <i>eInformationClass</i> parameter is equal to <b>ClfsLogBasicInformation</b>, <b>ClfsQueryLogFileInformation</b> returns information in a <b>CLFS_INFORMATION</b> structure. Most of the structure members hold information about a CLFS physical log, but if the log is multiplexed, certain members hold information that is specific to a particular stream. The following structure members hold information that is specific to a stream rather than the underlying physical log:

<ul>
<li>
<b>TotalUndoCommitment</b>

</li>
<li>
<b>Attributes</b>

</li>
<li>
<b>BaseLsn</b>

</li>
<li>
<b>LastLsn</b>

</li>
<li>
<b>RestartLsn</b>

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541679">ClfsQueryLogFileInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541761">ClfsSetLogFileInformation</a>
 

 

