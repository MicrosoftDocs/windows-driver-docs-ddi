---
UID: NS:mountdev._MOUNTDEV_SUGGESTED_LINK_NAME
title: _MOUNTDEV_SUGGESTED_LINK_NAME (mountdev.h)
description: Mount manager clients that are able to keep track of their drive letters use this structure to request that the mount manager assign them a particular link name.
old-location: storage\mountdev_suggested_link_name.htm
tech.root: storage
ms.assetid: 5c6e3337-8071-486a-826a-ade722eb8449
ms.date: 03/29/2018
keywords: ["MOUNTDEV_SUGGESTED_LINK_NAME structure"]
ms.keywords: "*PMOUNTDEV_SUGGESTED_LINK_NAME, MOUNTDEV_SUGGESTED_LINK_NAME, MOUNTDEV_SUGGESTED_LINK_NAME structure [Storage Devices], PMOUNTDEV_SUGGESTED_LINK_NAME, PMOUNTDEV_SUGGESTED_LINK_NAME structure pointer [Storage Devices], _MOUNTDEV_SUGGESTED_LINK_NAME, mountdev/MOUNTDEV_SUGGESTED_LINK_NAME, mountdev/PMOUNTDEV_SUGGESTED_LINK_NAME, storage.mountdev_suggested_link_name, structs-mntmgr_fc4a3528-34b9-4112-9501-87db4e87f9f3.xml"
f1_keywords:
 - "mountdev/MOUNTDEV_SUGGESTED_LINK_NAME"
 - "MOUNTDEV_SUGGESTED_LINK_NAME"
req.header: mountdev.h
req.include-header: Mountmgr.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mountdev.h
api_name:
- MOUNTDEV_SUGGESTED_LINK_NAME
targetos: Windows
req.typenames: MOUNTDEV_SUGGESTED_LINK_NAME, *PMOUNTDEV_SUGGESTED_LINK_NAME
---

# _MOUNTDEV_SUGGESTED_LINK_NAME structure

## -description

Mount manager clients that are able to keep track of their drive letters use this structure to request that the mount manager assign them a particular link name.

## -struct-fields

### -field UseOnlyIfThereAreNoOtherLinks

Indicates that the mount manager should use the suggested link name only if there are no other persistent links assigned to the client.

### -field NameLength

Contains the length of the suggested name. 

### -field Name

Contains a variable-sized array of wide characters that holds the name of the suggested link in wide characters. Drive letter names must include the full path of the symbolic link in object namespace and must have the traditional Microsoft MS-DOS syntax. For instance, drive letter "D" must be represented in this manner: "\DosDevices\D:". The alternative symbolic link path of "\??\D:" may not be used, nor may abbreviations of the symbolic link such as "D:". 

## -remarks

As a best practice, the implementer must not thread synchronize and must not make blocking and/or Interprocess Communication (IPC) function calls.

## -see-also

[IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME](ni-mountdev-ioctl_mountdev_query_suggested_link_name.md)
