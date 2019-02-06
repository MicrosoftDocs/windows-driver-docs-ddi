---
UID: NS:ntdddump._FILTER_EXTENSION
title: _FILTER_EXTENSION (ntdddump.h)
description: The crash dump driver passes a pointer to a FILTER_EXTENSION structure when the filter driver callback routines are called.
old-location: storage\filter_extension.htm
tech.root: storage
ms.assetid: 1113e917-3273-4ba7-8702-fe90a22fb024
ms.date: 03/29/2018
ms.keywords: "*PFILTER_EXTENSION, FILTER_EXTENSION, FILTER_EXTENSION structure [Storage Devices], PFILTER_EXTENSION, PFILTER_EXTENSION structure pointer [Storage Devices], _FILTER_EXTENSION, ntdddump/FILTER_EXTENSION, ntdddump/PFILTER_EXTENSION, storage.filter_extension, structs-filter_c9e640bb-9678-4e2f-9341-0d26b36e65e6.xml"
ms.topic: struct
req.header: ntdddump.h
req.include-header: Ntdddump.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista and Windows Server 2008.
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
-	ntdddump.h
api_name:
-	FILTER_EXTENSION
product:
- Windows
targetos: Windows
req.typenames: FILTER_EXTENSION, *PFILTER_EXTENSION
---

# _FILTER_EXTENSION structure


## -description


The crash dump driver passes a pointer to a FILTER_EXTENSION structure when the filter driver callback routines are called.


## -struct-fields




### -field DumpType

This parameter indicates the type of dump that this instance of the filter driver is loaded on.


### -field DeviceObject

A pointer to the device object of the dump volume. This pointer points to the top of the dump volume stack.


### -field Geometry

The disk geometry of the dump device in <a href="https://msdn.microsoft.com/library/windows/hardware/ff552613">DISK_GEOMETRY</a> format.


### -field DiskSize

Size of the disk.


### -field PartitionInfo

The partition information in <a href="https://msdn.microsoft.com/library/windows/hardware/ff552629">DISK_PARTITION_INFO</a> format.


### -field DumpData

A pointer to the context data that is provided by the filter driver in <a href="https://msdn.microsoft.com/library/windows/hardware/ff553865">FILTER_INITIALIZATION_DATA</a>.


### -field Size

 


### -field Flags

 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552613">DISK_GEOMETRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552629">DISK_PARTITION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553865">FILTER_INITIALIZATION_DATA</a>
 

 

