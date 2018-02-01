---
UID: NS:61883._SET_UNIT_DIRECTORY
title: "_SET_UNIT_DIRECTORY"
author: windows-driver-content
description: This structure is used to assign settings for a unit directory.
old-location: ieee\set_unit_directory.htm
old-project: IEEE
ms.assetid: C4021856-835D-4B4B-9795-4FEEEFAC06B8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PSET_UNIT_DIRECTORY structure pointer [Buses], SET_UNIT_DIRECTORY structure [Buses], _SET_UNIT_DIRECTORY, PSET_UNIT_DIRECTORY, 61883/PSET_UNIT_DIRECTORY, SET_UNIT_DIRECTORY, 61883/SET_UNIT_DIRECTORY, *PSET_UNIT_DIRECTORY, IEEE.set_unit_directory
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	61883.h
apiname:
-	SET_UNIT_DIRECTORY
product: Windows
targetos: Windows
req.typenames: "*PSET_UNIT_DIRECTORY, SET_UNIT_DIRECTORY"
---

# _SET_UNIT_DIRECTORY structure


## -description


This structure is used to assign settings for a unit directory.  The  request exposes a unit directory within the configuration ROM of the local host. This request is used to create or remove a Configuration ROM entry in the configuration ROM of a local node. A driver is responsible for removing the Configuration ROM entries it has created before the system unloads the driver. 


## -syntax


````
typedef struct _SET_UNIT_DIRECTORY {
  ULONG  Flags;
  ULONG  UnitSpecId;
  ULONG  UnitSwVersion;
  HANDLE hCromEntry;
} SET_UNIT_DIRECTORY, *PSET_UNIT_DIRECTORY;
````


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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20SET_UNIT_DIRECTORY structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

