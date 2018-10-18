---
UID: NS:wdm._CLS_CONTAINER_INFORMATION
title: "_CLS_CONTAINER_INFORMATION"
author: windows-driver-content
description: The CLFS_CONTAINER_INFORMATION structure holds descriptive information for an individual container in a Common Log File System (CLFS) log.
old-location: kernel\clfs_container_information.htm
tech.root: kernel
ms.assetid: 9e083aba-1039-4ad3-9650-0e6e38ceb0c0
ms.date: 04/30/2018
ms.keywords: "*PCLFS_CONTAINER_INFORMATION, *PCLS_CONTAINER_INFORMATION, CLFS_CONTAINER_INFORMATION, CLFS_CONTAINER_INFORMATION structure [Kernel-Mode Driver Architecture], CLS_CONTAINER_INFORMATION, CLS_CONTAINER_INFORMATION structure [Kernel-Mode Driver Architecture], PCLFS_CONTAINER_INFORMATION, PCLFS_CONTAINER_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PCLS_CONTAINER_INFORMATION, PCLS_CONTAINER_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PPCLFS_CONTAINER_INFORMATION, PPCLFS_CONTAINER_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PPCLS_CONTAINER_INFORMATION, PPCLS_CONTAINER_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _CLS_CONTAINER_INFORMATION, kernel.clfs_container_information, kstruct_a_757d7a17-feb2-4b99-8b6f-f83288858851.xml, wdm/CLFS_CONTAINER_INFORMATION, wdm/CLS_CONTAINER_INFORMATION, wdm/PCLFS_CONTAINER_INFORMATION, wdm/PCLS_CONTAINER_INFORMATION, wdm/PPCLFS_CONTAINER_INFORMATION, wdm/PPCLS_CONTAINER_INFORMATION"
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
-	CLS_CONTAINER_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: CLS_CONTAINER_INFORMATION, *PCLS_CONTAINER_INFORMATION, PPCLS_CONTAINER_INFORMATION
---

# _CLS_CONTAINER_INFORMATION structure


## -description


The <b>CLFS_CONTAINER_INFORMATION</b> structure holds descriptive information for an individual container in a Common Log File System (CLFS) log.


## -struct-fields




### -field FileAttributes

A set of flags that specifies attributes of the container. See the <i>fFlagsAndAttributes</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a> function.


### -field CreationTime

The time that the container was created.


### -field LastAccessTime

The time that the container was last accessed.


### -field LastWriteTime

The time of the last write to the container.


### -field ContainerSize

The size, in bytes, of the container.


### -field FileNameActualLength

The size, in characters, of the actual file name of the container.


### -field FileNameLength

The size of the file name in the <b>FileName</b> buffer.


### -field FileName

An array of wide characters that holds the file name of the container.


### -field State

An integer that specifies the state of the container. This member must be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>ClfsContainerInitializing</b>

</td>
<td>
The container has not yet been initialized.

</td>
</tr>
<tr>
<td>
<b>ClfsContainerInactive</b>

</td>
<td>
The container has been initialized but does not hold any records that are in the active portion of the log. 

</td>
</tr>
<tr>
<td>
<b>ClfsContainerActive</b>

</td>
<td>
The container is being used to hold records that belong to the active portion of the log.

</td>
</tr>
<tr>
<td>
<b>ClfsContainerActivePendingDelete</b>

</td>
<td>
The container is marked for deletion, but still holds records that belong to the active portion of the log.

</td>
</tr>
<tr>
<td>
<b>ClfsContainerPendingArchive</b>

</td>
<td>
The container is pending archival.

</td>
</tr>
<tr>
<td>
<b>ClfsContainerPendingArchiveAndDelete</b>

</td>
<td>
The container is marked for deletion, but still contains records that are pending archival.

</td>
</tr>
</table>
 


### -field PhysicalContainerId

A 32-bit identifier that remains the same over the life of the log.


### -field LogicalContainerId

A 32-bit identifier that changes every time the container is recycled.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff541737">ClfsScanLogContainers</a> function writes descriptive information into an array of <b>CLFS_CONTAINER_INFORMATION</b> structures.

Time values <b>CreationTime</b>, <b>LastAccessTime</b>, and <b>LastWriteTime</b> are expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541856">CLFS_SCAN_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541527">ClfsCreateScanContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541737">ClfsScanLogContainers</a>
 

 

