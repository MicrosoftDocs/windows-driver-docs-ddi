---
UID: NS:ntifs._NETWORK_OPEN_ECP_CONTEXT
title: NETWORK_OPEN_ECP_CONTEXT (ntifs.h)
description: The NETWORK_OPEN_ECP_CONTEXT structure is used to interpret network extra create parameter (ECP) contexts on files.
old-location: ifsk\network_open_ecp_context.htm
tech.root: ifsk
ms.date: 11/24/2020
keywords: ["NETWORK_OPEN_ECP_CONTEXT structure"]
ms.keywords: "*PNETWORK_OPEN_ECP_CONTEXT, ECP_Structures_9cdb7dab-17df-47f3-b994-fca989b3442e.xml, NETWORK_OPEN_ECP_CONTEXT, NETWORK_OPEN_ECP_CONTEXT structure [Installable File System Drivers], PNETWORK_OPEN_ECP_CONTEXT, PNETWORK_OPEN_ECP_CONTEXT structure pointer [Installable File System Drivers], _NETWORK_OPEN_ECP_CONTEXT, ifsk.network_open_ecp_context, ntifs/NETWORK_OPEN_ECP_CONTEXT, ntifs/PNETWORK_OPEN_ECP_CONTEXT"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows Vista.
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
req.typenames: NETWORK_OPEN_ECP_CONTEXT, *PNETWORK_OPEN_ECP_CONTEXT
f1_keywords:
 - _NETWORK_OPEN_ECP_CONTEXT
 - ntifs/_NETWORK_OPEN_ECP_CONTEXT
 - PNETWORK_OPEN_ECP_CONTEXT
 - ntifs/PNETWORK_OPEN_ECP_CONTEXT
 - NETWORK_OPEN_ECP_CONTEXT
 - ntifs/NETWORK_OPEN_ECP_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _NETWORK_OPEN_ECP_CONTEXT
 - PNETWORK_OPEN_ECP_CONTEXT
 - NETWORK_OPEN_ECP_CONTEXT
---

# NETWORK_OPEN_ECP_CONTEXT structure


## -description

The **NETWORK_OPEN_ECP_CONTEXT** structure is used to interpret network extra create parameter (ECP) contexts on files.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Reserved

Reserved. Must be set to zero.

### -field DUMMYSTRUCTNAME

A structure that contains restrictions to apply for opening the file (pre-create) and to apply to the file after it is opened (post-create).

### -field DUMMYSTRUCTNAME.in

Structure that contains pre-create restrictions for opening a file.

### -field DUMMYSTRUCTNAME.in.Location

A [**NETWORK_OPEN_LOCATION_QUALIFIER**](ne-ntifs-network_open_location_qualifier.md)-typed value that specifies the location restriction to attach to the file.

### -field DUMMYSTRUCTNAME.in.Integrity

A [**NETWORK_OPEN_INTEGRITY_QUALIFIER**](ne-ntifs-network_open_integrity_qualifier.md)-typed value that specifies the integrity restriction to attach to the file.

### -field DUMMYSTRUCTNAME.in.Flags

Supported starting with Windows 7. A value that specifies attributes for the file. This member is a bitwise OR of any of the following flags.

| Value | Meaning |
| ----- | ------- |
| NETWORK_OPEN_ECP_IN_FLAG_DISABLE_HANDLE_COLLAPSING (0x1) | Indicates to the SMB redirector that the incoming open request must not be piggybacked and collapsed onto an existing open handle to the same file. |
| NETWORK_OPEN_ECP_IN_FLAG_DISABLE_HANDLE_DURABILITY (0x2) | Causes the SMB2+ redirector to disable durability on this open handle. For more information about opening a file for durable operation, see [Application Requests Creating a File Opened for Durable Operation](/openspecs/windows_protocols/ms-smb2/11d04fbc-2c15-4acc-807d-949b6605ed6c). |
| NETWORK_OPEN_ECP_IN_FLAG_DISABLE_OPLOCKS (0x4) | Indicates to the SMB redirector to not grant oplocks for the incoming open request. This flag is available starting with Windows 8. |
| NETWORK_OPEN_ECP_IN_FLAG_FORCE_BUFFERED_SYNCHRONOUS_IO_HACK (0x80000000) | Reserved for internal use and must not be used by applications. This flag forces the redirector to use synchronous I/O even though the handle was opened for asynchronous I/O. |

### -field DUMMYSTRUCTNAME.out

Structure that contains post-create restrictions to apply to a file after it has been opened.

### -field DUMMYSTRUCTNAME.out.Location

A [**NETWORK_OPEN_LOCATION_QUALIFIER**](ne-ntifs-network_open_location_qualifier.md)-typed value that specifies the location restriction to attach to the file.

### -field DUMMYSTRUCTNAME.out.Integrity

A [**NETWORK_OPEN_INTEGRITY_QUALIFIER**](ne-ntifs-network_open_integrity_qualifier.md)-typed value that specifies the integrity restriction to attach to the file.

### -field DUMMYSTRUCTNAME.out.Flags

 Supported starting with Windows 7. A value that specifies attributes for the file. This member is a bitwise OR of any of the following flags.

| Value | Meaning |
| ----- | ------- |
| NETWORK_OPEN_ECP_IN_FLAG_DISABLE_HANDLE_COLLAPSING (0x1) | Indicates to the SMB redirector that the incoming open request must not be piggybacked and collapsed onto an existing open handle to the same file. |
| NETWORK_OPEN_ECP_IN_FLAG_DISABLE_HANDLE_DURABILITY (0x2) | Causes the SMB2+ redirector to disable durability on this open handle. For more information about opening a file for durable operation, see [Application Requests Creating a File Opened for Durable Operation](/openspecs/windows_protocols/ms-smb2/11d04fbc-2c15-4acc-807d-949b6605ed6c). |
| NETWORK_OPEN_ECP_IN_FLAG_FORCE_BUFFERED_SYNCHRONOUS_IO_HACK (0x80000000) | Reserved for internal use and must not be used by applications. This flag forces the redirector to use synchronous I/O even though the handle was opened for asynchronous I/O. |

## -remarks

For information about how to use ECPs to associate extra information with a file when the file is created, see [Using Extra Create Parameters with an IRP_MJ_CREATE Operation](/windows-hardware/drivers/ifs/using-extra-create-parameters-with-an-irp-mj-create-operation).

A filter driver should consider the NETWORK_OPEN_ECP_CONTEXT structure to be read-only, using it only to retrieve information about the network ECP context on a file. For more information, see [System-Defined ECPs](/windows-hardware/drivers/ifs/system-defined-ecps).

If a caller must verify that the file system acknowledged the **NETWORK_OPEN_ECP_CONTEXT** context structure, the caller should call the [**FltIsEcpAcknowledged**](../fltkernel/nf-fltkernel-fltisecpacknowledged.md) or [**FsRtlIsEcpAcknowledged**](./nf-ntifs-fsrtlisecpacknowledged.md) routine on the ECP after the operation is complete.

Drivers that run on Windows 7 and later versions of Windows and that must interpret network ECP contexts on files that reside on Windows Vista must use the [**NETWORK_OPEN_ECP_CONTEXT_V0**](ns-ntifs-_network_open_ecp_context_v0.md) structure instead.

Drivers that run on Windows Vista and later versions of Windows use the **NETWORK_OPEN_ECP_CONTEXT** structure to interpret network ECP contexts on files. However, the **DUMMYSTRUCTNAME.in.Flags** and **DUMMYSTRUCTNAME.out.Flags** members are only supported starting with Windows 7.

## -see-also

[**FltIsEcpAcknowledged**](../fltkernel/nf-fltkernel-fltisecpacknowledged.md)

[**FsRtlIsEcpAcknowledged**](./nf-ntifs-fsrtlisecpacknowledged.md)

[**NETWORK_OPEN_ECP_CONTEXT_V0**](ns-ntifs-_network_open_ecp_context_v0.md)

[**NETWORK_OPEN_LOCATION_QUALIFIER**](ne-ntifs-network_open_location_qualifier.md)

[**NETWORK_OPEN_INTEGRITY_QUALIFIER**](ne-ntifs-network_open_integrity_qualifier.md)

