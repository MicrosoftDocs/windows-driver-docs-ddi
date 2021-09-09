---
UID: NS:ntifs._CREATE_REDIRECTION_ECP_CONTEXT
tech.root: ifsk
title: CREATE_REDIRECTION_ECP_CONTEXT
ms.date: 09/09/2021
targetos: Windows
description: Learn more about the CREATE_REDIRECTION_ECP_CONTEXT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.target-type: 
req.typenames: CREATE_REDIRECTION_ECP_CONTEXT, *PCREATE_REDIRECTION_ECP_CONTEXT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _CREATE_REDIRECTION_ECP_CONTEXT
 - PCREATE_REDIRECTION_ECP_CONTEXT
 - CREATE_REDIRECTION_ECP_CONTEXT
f1_keywords:
 - _CREATE_REDIRECTION_ECP_CONTEXT
 - ntifs/_CREATE_REDIRECTION_ECP_CONTEXT
 - PCREATE_REDIRECTION_ECP_CONTEXT
 - ntifs/PCREATE_REDIRECTION_ECP_CONTEXT
 - CREATE_REDIRECTION_ECP_CONTEXT
 - ntifs/CREATE_REDIRECTION_ECP_CONTEXT
dev_langs:
 - c++
---

## -description

The **CREATE_REDIRECTION_ECP_CONTEXT** structure contains the extra create parameter (ECP) context that can be sent to query the redirection state of a file for a specific create operation.

## -struct-fields

### -field Size

Size of this structure, in bytes.

### -field Flags

The redirection state of the file. Can be one of the following values.

| Flag | Meaning |
| CREATE_REDIRECTION_FLAGS_SERVICED_FROM_LAYER            | This is a redirected file from a layer that is not registered in the LayerRootLocations registry key. |
| CREATE_REDIRECTION_FLAGS_SERVICED_FROM_SCRATCH          | This is a new or modified file, it is not redirected. |
| CREATE_REDIRECTION_FLAGS_SERVICED_FROM_REGISTERED_LAYER | This is a redirected file from a layer that is listed in the LayerRootLocations registry key. |
| CREATE_REDIRECTION_FLAGS_SERVICED_FROM_REMOTE_LAYER     | This is a redirected file from a remote file system relative to the container. It may or may not be registered as a layer on that server. For Hyper-V containers, the remote server is the host of the Hyper-V container utility VM. |
| CREATE_REDIRECTION_FLAGS_SERVICED_FROM_USER_MODE        | This is a cloud or other file that requires user-mode redirection. |

### -field FileId

The file ID.

### -field VolumeGuid

The volume GUID.

## -remarks

The system-defined GUID_ECP_CREATE_REDIRECTION value is used with this ECP context structure when calling ECP-related support routines such as [**FltAllocateExtraCreateParameter**](../fltkernel/nf-fltkernel-fltallocateextracreateparameter.md) and [**FsRtlRemoveExtraCreateParameter**](nf-ntifs-fsrtlremoveextracreateparameter.md).

See [Introduction to extra create parameters](/windows-hardware/drivers/ifs/introduction-to-extra-create-parameters) for more information.
