---
UID: NS:ntdddisk._DISK_PERFORMANCE
title: "_DISK_PERFORMANCE"
author: windows-driver-content
description: The DISK_PERFORMANCE structure is used in conjunction with the IOCTL_DISK_PERFORMANCE request to collect summary disk statistics for purposes of measuring disk performance.
old-location: storage\disk_performance.htm
old-project: storage
ms.assetid: 34d954db-4220-4a3f-849c-f1164e6130f7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDISK_PERFORMANCE, DISK_PERFORMANCE, DISK_PERFORMANCE structure [Storage Devices], PDISK_PERFORMANCE, PDISK_PERFORMANCE structure pointer [Storage Devices], _DISK_PERFORMANCE, ntdddisk/DISK_PERFORMANCE, ntdddisk/PDISK_PERFORMANCE, storage.disk_performance, structs-disk_64493b27-dce7-4976-9519-c7324bd09b69.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	ntdddisk.h
api_name:
-	DISK_PERFORMANCE
product: Windows
targetos: Windows
req.typenames: DISK_PERFORMANCE, *PDISK_PERFORMANCE
---

# _DISK_PERFORMANCE structure


## -description


The DISK_PERFORMANCE structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560388">IOCTL_DISK_PERFORMANCE</a> request to collect summary disk statistics for purposes of measuring disk performance. 


## -struct-fields




### -field BytesRead

Contains a cumulative count of bytes read from the disk since the performance counters were enabled. 


### -field BytesWritten

Contains a cumulative count of bytes written to the disk since the performance counters were enabled.


### -field ReadTime

Contains a cumulative time, expressed in increments of 100 nanoseconds, spent on disk reads since the performance counters were enabled. 


### -field WriteTime

Contains a cumulative time, expressed in increments of 100 nanoseconds, spent on disk reads since the performance counters were enabled. 


### -field IdleTime

Contains a cumulative time, expressed in increments of 100 nanoseconds, since the performance counters were enabled in which there was no disk activity. 


### -field ReadCount

Contains the number of disk accesses for reads since the performance counters were enabled. 


### -field WriteCount

Contains the number of disk accesses for writes since the performance counters were enabled.


### -field QueueDepth

Contains a snapshot of the number of queued disk I/O requests at the time that the query for performance statistics was performed. 


### -field SplitCount

Contains the number of disk accesses by means of an associated IRP since the performance counters were enabled. 


### -field QueryTime

Contains a timestamp indicating the system time at the moment that the query took place. System time is a count of 100-nanosecond intervals since January 1, 1601. System time is typically updated approximately every ten milliseconds. For more information about system time, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553068">KeQuerySystemTime</a>.


### -field StorageDeviceNumber

Contains a unique number assigned to every disk or volume across a particular storage type. The storage types are <i>disk.sys</i>, <i>ftdisk.sys</i>, and <i>dmio.sys</i>. 


### -field StorageManagerName

Contains an 8-character string that indicates which device driver provided the performance statistics. In Windows 2000, this can be either "LogiDisk" for the driver <i>logidisk.sys</i> or "PhysDisk" for the driver <i>physdisk.sys</i>. These drivers collect performance statistics for devices and physical disks respectively. In Windows XP and later operating systems, this can be any of the following three strings: "FTDISK" for the driver <i>ftdisk.sys</i>, "DMIO" for the driver <i>dmio.sys</i>, or PARTMGR" for the driver <i>partmgr.sys</i>. These three drivers collect performance statistics for basic disk volumes, dynamic disk volumes, and physical disks respectively. Note that these strings are 8-character case-sensitive strings with blank fill. For example, in the case of the string "FTDISK", the <b>StorageManagerName</b> character array should contain two trailing blanks ("FTDISK&lt;b&gt;&lt;b&gt;"), and in the case of the string "DMIO", the array should contain four trailing blanks ("DMIO&lt;b&gt;&lt;b&gt;&lt;b&gt;&lt;b&gt;").


## -remarks



Counting halts whenever the performance counters are disabled, but the counters are not reset, so the cumulative values assigned to the structure members might potentially reflect disk activity across several enablings and disablings of the counters. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560388">IOCTL_DISK_PERFORMANCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560393">IOCTL_DISK_PERFORMANCE_OFF</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_PERFORMANCE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

