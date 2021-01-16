---
UID: NS:ntifs._FILE_REMOTE_PROTOCOL_INFORMATION
title: FILE_REMOTE_PROTOCOL_INFORMATION
description: The FILE_REMOTE_PROTOCOL_INFORMATION structure contains file remote protocol information.
tech.root: ifsk
ms.date: 08/19/2019
keywords: ["FILE_REMOTE_PROTOCOL_INFORMATION structure"]
ms.keywords: FILE_REMOTE_PROTOCOL_INFORMATION, FILE_REMOTE_PROTOCOL_INFORMATION, *PFILE_REMOTE_PROTOCOL_INFORMATION,
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: FILE_REMOTE_PROTOCOL_INFORMATION, *PFILE_REMOTE_PROTOCOL_INFORMATION
targetos: Windows
f1_keywords:
 - _FILE_REMOTE_PROTOCOL_INFORMATION
 - ntifs/_FILE_REMOTE_PROTOCOL_INFORMATION
 - PFILE_REMOTE_PROTOCOL_INFORMATION
 - ntifs/PFILE_REMOTE_PROTOCOL_INFORMATION
 - FILE_REMOTE_PROTOCOL_INFORMATION
 - ntifs/FILE_REMOTE_PROTOCOL_INFORMATION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_REMOTE_PROTOCOL_INFORMATION
 - PFILE_REMOTE_PROTOCOL_INFORMATION
 - FILE_REMOTE_PROTOCOL_INFORMATION
product:
 - Windows
---

# FILE_REMOTE_PROTOCOL_INFORMATION structure


## -description

The *FILE_REMOTE_PROTOCOL_INFORMATION* structure contains file remote protocol information.  This structure is returned from [FltQueryInformationFile](../fltkernel/nf-fltkernel-fltqueryinformationfile.md) when **FileRemoteProtocolInformation** is passed in as the *FileInformationClass* parameter.

## -struct-fields

### -field StructureVersion

Version of this structure. Set this member as follows.

| Value | Meaning |
|-------|---------|
|   1   | Communication is between computers running Windows 7 |
|   2   | Communication is between computers running Windows 8 |
|   3   | Communication is between computers running Windows 8.1 |
|   4   | Communication is between computers running Windows 10 or later |

### -field StructureSize

Size of this structure, in bytes. This member should be set to **sizeof**(FILE_REMOTE_PROTOCOL_INFORMATION).

### -field Protocol

One of the **WNNC_NET_*XXX*** remote protocol network types defined in *ntifs.h*.

### -field ProtocolMajorVersion

Major number of the remote protocol.

### -field ProtocolMinorVersion

Minor number of the remote protocol.

### -field ProtocolRevision

Revision of the remote protocol.

### -field Reserved

Should be set to zero. Do not use this member.

### -field Flags

Remote protocol information. This member can be set to zero or more of the following flags.

| Value | Meaning |
| ----- | ------- |
| REMOTE_PROTOCOL_FLAG_LOOPBACK | The remote protocol is using a loopback |
| REMOTE_PROTOCOL_FLAG_OFFLINE | The remote protocol is using an offline cache |
| REMOTE_PROTOCOL_INFO_FLAG_PERSISTENT_HANDLE | The remote protocol is using a persistent handle. This flag is supported only if **StructureVersion** is 2 or higher. |
| REMOTE_PROTOCOL_INFO_FLAG_PRIVACY | The remote protocol is using privacy. This flag is supported only if **StructureVersion** is 2 or higher. |
| REMOTE_PROTOCOL_INFO_FLAG_INTEGRITY | The remote protocol is using integrity so the data is signed. This flag is supported only if **StructureVersion** is 2 or higher. |
| REMOTE_PROTOCOL_INFO_FLAG_MUTUAL_AUTH | The remote protocol is using mutual authentication using Kerberos. This flag is supported only if **StructureVersion** is 2 or higher. |

### -field GenericReserved

Protocol-generic information structure.

### -field GenericReserved.Reserved

Should be set to zero. Do not use this member.

### -field ProtocolSpecificReserved

### -field ProtocolSpecificReserved.Reserved

### -field ProtocolSpecific

### -field ProtocolSpecific.Smb2

### -field ProtocolSpecific.Smb2.Server

### -field ProtocolSpecific.Smb2.Server.Capabilities

### -field ProtocolSpecific.Smb2.Share

### -field ProtocolSpecific.Smb2.Share.Capabilities

### -field ProtocolSpecific.Smb2.Share.CachingFlags

### -field ProtocolSpecific.Smb2.Share.ShareType

### -field ProtocolSpecific.Smb2.Share.Reserved0

### -field ProtocolSpecific.Smb2.Share.Reserved1

### -field ProtocolSpecific.Reserved

## -remarks

## -see-also

[FILE_INFORMATION_CLASS](../wdm/ne-wdm-_file_information_class.md)

[FltQueryInformationFile](../fltkernel/nf-fltkernel-fltqueryinformationfile.md)

