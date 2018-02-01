---
UID: NS:mountdev._MOUNTDEV_SUGGESTED_LINK_NAME
title: "_MOUNTDEV_SUGGESTED_LINK_NAME"
author: windows-driver-content
description: Mount manager clients that are able to keep track of their drive letters use this structure to request that the mount manager assign them a particular link name.
old-location: storage\mountdev_suggested_link_name.htm
old-project: storage
ms.assetid: 5c6e3337-8071-486a-826a-ade722eb8449
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PMOUNTDEV_SUGGESTED_LINK_NAME structure pointer [Storage Devices], *PMOUNTDEV_SUGGESTED_LINK_NAME, storage.mountdev_suggested_link_name, mountdev/PMOUNTDEV_SUGGESTED_LINK_NAME, mountdev/MOUNTDEV_SUGGESTED_LINK_NAME, MOUNTDEV_SUGGESTED_LINK_NAME, structs-mntmgr_fc4a3528-34b9-4112-9501-87db4e87f9f3.xml, PMOUNTDEV_SUGGESTED_LINK_NAME, MOUNTDEV_SUGGESTED_LINK_NAME structure [Storage Devices], _MOUNTDEV_SUGGESTED_LINK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mountdev.h
apiname:
-	MOUNTDEV_SUGGESTED_LINK_NAME
product: Windows
targetos: Windows
req.typenames: MOUNTDEV_SUGGESTED_LINK_NAME, *PMOUNTDEV_SUGGESTED_LINK_NAME
---

# _MOUNTDEV_SUGGESTED_LINK_NAME structure


## -description


Mount manager clients that are able to keep track of their drive letters use this structure to request that the mount manager assign them a particular link name. 


## -syntax


````
typedef struct _MOUNTDEV_SUGGESTED_LINK_NAME {
  BOOLEAN UseOnlyIfThereAreNoOtherLinks;
  USHORT  NameLength;
  WCHAR   Name[1];
} MOUNTDEV_SUGGESTED_LINK_NAME, *PMOUNTDEV_SUGGESTED_LINK_NAME;
````


## -struct-fields




### -field UseOnlyIfThereAreNoOtherLinks

Indicates that the mount manager should use the suggested link name only if there are no other persistent links assigned to the client. 


### -field NameLength

Contains the length of the suggested name. 


### -field Name

Contains a variable-sized array of wide characters that holds the name of the suggested link in wide characters. Drive letter names must include the full path of the symbolic link in object namespace and must have the traditional Microsoft MS-DOS syntax. For instance, drive letter "D" must be represented in this manner: "\DosDevices\D:". The alternative symbolic link path of "\??\D:" may not be used, nor may abbreviations of the symbolic link such as "D:". 


## -see-also

<a href="..\mountdev\ni-mountdev-ioctl_mountdev_query_suggested_link_name.md">IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MOUNTDEV_SUGGESTED_LINK_NAME structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

