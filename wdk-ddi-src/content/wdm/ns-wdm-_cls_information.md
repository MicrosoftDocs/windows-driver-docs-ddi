---
UID: NS:wdm._CLS_INFORMATION
title: "_CLS_INFORMATION"
author: windows-driver-content
description: The CLFS_INFORMATION structure holds metadata and state information for a Common Log File System (CLFS) stream and/or its underlying physical log.
old-location: kernel\clfs_information.htm
old-project: kernel
ms.assetid: 7fe392d1-75e4-43b1-a09b-6f47981bef7e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/PCLS_INFORMATION, _CLS_INFORMATION, PCLFS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PPCLS_INFORMATION, *PPCLS_INFORMATION, PPCLS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PCLS_INFORMATION, wdm/CLS_INFORMATION, kstruct_a_6935868e-7d3d-458e-a556-0c92ed99bdbf.xml, wdm/PPCLFS_INFORMATION, *PCLS_INFORMATION, PPCLFS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], CLS_INFORMATION, wdm/CLFS_INFORMATION, *PCLFS_INFORMATION, CLFS_INFORMATION, CLFS_INFORMATION structure [Kernel-Mode Driver Architecture], PCLFS_INFORMATION, wdm/PPCLS_INFORMATION, PCLS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], wdm/PCLFS_INFORMATION, CLS_INFORMATION structure [Kernel-Mode Driver Architecture], PPCLFS_INFORMATION, kernel.clfs_information
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	CLS_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PCLS_INFORMATION, *PPCLS_INFORMATION, CLS_INFORMATION"
req.product: Windows 10 or later.
---

# _CLS_INFORMATION structure


## -description


The <b>CLFS_INFORMATION</b> structure holds metadata and state information for a Common Log File System (CLFS) stream and/or its underlying physical log.


## -syntax


````
typedef struct _CLS_INFORMATION {
  LONGLONG  TotalAvailable;
  LONGLONG  CurrentAvailable;
  LONGLONG  TotalReservation;
  ULONGLONG BaseFileSize;
  ULONGLONG ContainerSize;
  ULONG     TotalContainers;
  ULONG     FreeContainers;
  ULONG     TotalClients;
  ULONG     Attributes;
  ULONG     FlushThreshold;
  ULONG     SectorSize;
  CLFS_LSN  MinArchiveTailLsn;
  CLFS_LSN  BaseLsn;
  CLFS_LSN  LastFlushedLsn;
  CLFS_LSN  LastLsn;
  CLFS_LSN  RestartLsn;
  GUID      Identity;
} CLS_INFORMATION, *PCLS_INFORMATION, *PPCLS_INFORMATION, CLFS_INFORMATION, *PCLFS_INFORMATION, *PPCLFS_INFORMATION;
````


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

A set of flags that specify stream (or physical log) attributes. See the <i>fFlagsAndAttributes</i> parameter of the <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a> function.


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



The <a href="..\wdm\nf-wdm-clfsquerylogfileinformation.md">ClfsQueryLogFileInformation</a> function returns information about a CLFS stream and/or its underlying physical log. The type of information returned depends on the <i>eInformationClass</i> parameter. 

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

<a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>





<a href="..\wdm\nf-wdm-clfssetlogfileinformation.md">ClfsSetLogFileInformation</a>



<a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLS_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

