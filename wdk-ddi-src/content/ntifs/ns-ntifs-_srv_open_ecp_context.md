---
UID: NS:ntifs._SRV_OPEN_ECP_CONTEXT
title: _SRV_OPEN_ECP_CONTEXT (ntifs.h)
description: The SRV_OPEN_ECP_CONTEXT structure is used by a server to conditionally open files in response to client requests.
old-location: ifsk\srv_open_ecp_context.htm
tech.root: ifsk
ms.assetid: 6860f512-758d-4a75-88e4-17310b3e6349
ms.date: 09/09/2019
keywords: ["SRV_OPEN_ECP_CONTEXT structure"]
ms.keywords: "*PSRV_OPEN_ECP_CONTEXT, ECP_Structures_1a5afc2a-f4a5-4f86-ac30-2e206778acc0.xml, PSRV_OPEN_ECP_CONTEXT, PSRV_OPEN_ECP_CONTEXT structure pointer [Installable File System Drivers], SRV_OPEN_ECP_CONTEXT, SRV_OPEN_ECP_CONTEXT structure [Installable File System Drivers], _SRV_OPEN_ECP_CONTEXT, ifsk.srv_open_ecp_context, ntifs/PSRV_OPEN_ECP_CONTEXT, ntifs/SRV_OPEN_ECP_CONTEXT"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows 7.
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
targetos: Windows
req.typenames: SRV_OPEN_ECP_CONTEXT, *PSRV_OPEN_ECP_CONTEXT
f1_keywords:
 - _SRV_OPEN_ECP_CONTEXT
 - ntifs/_SRV_OPEN_ECP_CONTEXT
 - PSRV_OPEN_ECP_CONTEXT
 - ntifs/PSRV_OPEN_ECP_CONTEXT
 - SRV_OPEN_ECP_CONTEXT
 - ntifs/SRV_OPEN_ECP_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - SRV_OPEN_ECP_CONTEXT
---

# _SRV_OPEN_ECP_CONTEXT structure


## -description

The SRV_OPEN_ECP_CONTEXT structure is used by a server to conditionally open files in response to client requests.

## -struct-fields

### -field ShareName

Pointer to a [UNICODE_STRING](https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that supplies the share name for the server that contains the files to be open. This field is optional and can be NULL.

### -field SocketAddress

Pointer to a [SOCKADDR_STORAGE](https://docs.microsoft.com/windows/win32/api/ws2def/ns-ws2def-sockaddr_storage_lh) structure that specifies the transport address of a client computer. This client originates the open file request. This field is optional and can be a NULL.

### -field OplockBlockState

A Boolean value that indicates whether the Server Message Block (SMB) server blocks the open thread that is waiting for the oplock break. **TRUE** indicates that the open thread is in the blocking state and **FALSE** otherwise.

### -field OplockAppState

A Boolean value that indicates whether the SMB server requests an oplock with the current open thread. Set to **TRUE** to request the oplock and **FALSE** otherwise.

### -field OplockFinalState

A Boolean value that indicates whether a file-open operation is the final file-open operation to request the oplock. **TRUE** indicates the final file-open operation to obtain the oplock and **FALSE** indicates otherwise.

### -field Version

Version of this structure. This member was added in Windows 10 version 1703, so before trying to access it you must first check to see if it exists. If the structure size is >= [RTL_SIZEOF_THROUGH_FIELD](https://docs.microsoft.com/windows-hardware/drivers/debugger/c---numbers-and-operators)(SRV_OPEN_ECP_CONTEXT, Version), you can access this field. This member can be currently be set to SRV_OPEN_ECP_CONTEXT_VERSION_2.

### -field InstanceType

The [SRV_INSTANCE_TYPE](ne-ntifs-srv_instance_type.md) that the open is coming from. File system minifilters that attach to NTFS or ReFS used by CSVFS can use this field to detect if this open is bypassing CSVFS. If the open goes through CSVFS, then this ECP is either absent or the instance type is SrvInstanceTypeCsv. If the open is bypassing CSVFS and goes directly to the hidden volume, then **InstanceType** is SrvInstanceTypePrimary. The **InstanceType** field is present only if **Version** is >= SRV_OPEN_ECP_CONTEXT_VERSION_2.

## -remarks

The file-system stack can determine whether SRV_OPEN_ECP_CONTEXT is attached to the create file request. The file-system stack can then use the information in SRV_OPEN_ECP_CONTEXT to determine which client requested that the file be opened, and why it requested it. For information about how to retrieve the SRV_OPEN_ECP_CONTEXT extra information that is attached to a create file request, see [Retrieving ECPs](https://docs.microsoft.com/windows-hardware/drivers/ifs/using-ecps-to-process-irp-mj-create-operations-in-a-file-system-filter).

The SRV_OPEN_ECP_CONTEXT structure is read-only. You should use it to retrieve information about a server open ECP only. For more information about this issue, see [System-Defined ECPs](https://docs.microsoft.com/windows-hardware/drivers/ifs/system-defined-ecps).

The oplock state values (**OplockBlockState**, **OplockAppState**, and **OplockFinalState**) are used with oplock breaking logic for system management for SMB and SMB2.

## -see-also

[SOCKADDR_STORAGE](https://docs.microsoft.com/windows/win32/api/ws2def/ns-ws2def-sockaddr_storage_lh)

[SRV_INSTANCE_TYPE](ne-ntifs-srv_instance_type.md)

[UNICODE_STRING](https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

