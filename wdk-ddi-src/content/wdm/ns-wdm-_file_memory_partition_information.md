---
UID: NS:wdm._FILE_MEMORY_PARTITION_INFORMATION
title: _FILE_MEMORY_PARTITION_INFORMATION
author: windows-driver-content
description: Stores information about memory partition. This structure is used by the ZwSetInformationFile function.
old-location: ifsk\_file_memory_partition_information.htm
old-project: ifsk
ms.assetid: 1d74aec3-dbc5-4494-ba52-135e3f545c1b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _FILE_MEMORY_PARTITION_INFORMATION, *PFILE_MEMORY_PARTITION_INFORMATION, FILE_MEMORY_PARTITION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_MEMORY_PARTITION_INFORMATION
req.alt-loc: Wdm.h
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
req.typenames: *PFILE_MEMORY_PARTITION_INFORMATION, FILE_MEMORY_PARTITION_INFORMATION
req.product: Windows 10 or later.
---

# _FILE_MEMORY_PARTITION_INFORMATION structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Stores information about memory partition. This structure is used by the <b>ZwSetInformationFile</b> function.



## -syntax

````
typedef struct _FILE_MEMORY_PARTITION_INFORMATION {
  ULONG_PTR OwnerPartitionHandle;
  union {
    struct {
      UCHAR NoCrossPartitionAccess;
      UCHAR Spare[3];
    } DUMMYSTRUCTNAME;
    ULONG AllFlags;
  } Flags;
} FILE_MEMORY_PARTITION_INFORMATION, FILE_MEMORY_PARTITION_INFORMATION;
````


## -struct-fields

### -field OwnerPartitionHandle

Handle to the specified partition.


### -field Flags


### -field DUMMYSTRUCTNAME


### -field NoCrossPartitionAccess

Determines whether cross-partition access is allowed.

</dd>
</dl>

### -field AllFlags

Bitwise of all flags. 

</dd>
</dl>

## -remarks
