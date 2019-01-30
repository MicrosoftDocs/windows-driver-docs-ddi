---
UID: NS:61883._SET_UNIT_DIRECTORY
title: "_SET_UNIT_DIRECTORY" (61883.h)
description: This structure is used to assign settings for a unit directory.
old-location: ieee\set_unit_directory.htm
tech.root: IEEE
ms.assetid: C4021856-835D-4B4B-9795-4FEEEFAC06B8
ms.date: 02/15/2018
ms.keywords: "*PSET_UNIT_DIRECTORY, 61883/PSET_UNIT_DIRECTORY, 61883/SET_UNIT_DIRECTORY, IEEE.set_unit_directory, PSET_UNIT_DIRECTORY, PSET_UNIT_DIRECTORY structure pointer [Buses], SET_UNIT_DIRECTORY, SET_UNIT_DIRECTORY structure [Buses], _SET_UNIT_DIRECTORY"
ms.topic: struct
req.header: 61883.h
req.include-header: 
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
-	61883.h
api_name:
-	SET_UNIT_DIRECTORY
product:
- Windows
targetos: Windows
req.typenames: SET_UNIT_DIRECTORY, *PSET_UNIT_DIRECTORY
---

# _SET_UNIT_DIRECTORY structure


## -description


This structure is used to assign settings for a unit directory.  The  request exposes a unit directory within the configuration ROM of the local host. This request is used to create or remove a Configuration ROM entry in the configuration ROM of a local node. A driver is responsible for removing the Configuration ROM entries it has created before the system unloads the driver. 


## -struct-fields




### -field Flags

On input, specifies whether to add or remove a unit directory. Can be ADD_UNIT_DIRECTORY_ENTRY to add a unit directory, or REMOVE_UNIT_DIRECTORY_ENTRY to remove a unit directory. If ISSUE_BUS_RESET_AFTER_MODIFY is also set, a bus reset will be issued after the add or remove.


### -field UnitSpecId

On input, the UnitSpecId value to use within the unit directory, as defined in the <i>IEEE 1394-1995 Specification</i>. 


### -field UnitSwVersion

On input, the UnitSwVersion value to use within the unit directory, as defined in the <i>IEEE 1394-1995 Specification</i>. 


### -field hCromEntry

On input, a handle to the Configuration ROM entry. 

If ADD-UNIT_DIRECTORY_ENTRY is set in <b>Flags</b>, <b>hCromEntry</b> is ignored. 

If REMOVE_UNIT_DIRECTORY_ENTRY is set in <b>Flags</b>, <b>hCromEntry</b> is a handle to the Configuration ROM entry to remove. 

On output, if ADD_UNIT_DIRECTORY_ENTRY is set in <b>Flags</b>, a handle to the newly added unit directory is written to <b>hCromEntry</b>. 

If REMOVE_UNIT_DIRECTORY_ENTRY is set in Flags, <b>hCromEntry</b> is null.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

