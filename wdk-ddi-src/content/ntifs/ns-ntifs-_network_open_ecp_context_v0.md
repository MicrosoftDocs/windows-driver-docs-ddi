---
UID: NS:ntifs._NETWORK_OPEN_ECP_CONTEXT_V0
title: _NETWORK_OPEN_ECP_CONTEXT_V0 (ntifs.h)
description: The NETWORK_OPEN_ECP_CONTEXT_V0 structure is used to interpret network extra create parameter (ECP) contexts on files.
old-location: ifsk\network_open_ecp_context_v0.htm
tech.root: ifsk
ms.assetid: 447d623a-88cb-4d3d-8b05-4f5624c707ad
ms.date: 06/10/2020
keywords: ["NETWORK_OPEN_ECP_CONTEXT_V0 structure"]
ms.keywords: "*PNETWORK_OPEN_ECP_CONTEXT_V0, ECP_Structures_8bd64f25-774a-4f87-a903-07ce0a3c0989.xml, NETWORK_OPEN_ECP_CONTEXT_V0, NETWORK_OPEN_ECP_CONTEXT_V0 structure [Installable File System Drivers], PNETWORK_OPEN_ECP_CONTEXT_V0, PNETWORK_OPEN_ECP_CONTEXT_V0 structure pointer [Installable File System Drivers], _NETWORK_OPEN_ECP_CONTEXT_V0, ifsk.network_open_ecp_context_v0, ntifs/NETWORK_OPEN_ECP_CONTEXT_V0, ntifs/PNETWORK_OPEN_ECP_CONTEXT_V0"
f1_keywords:
 - "ntifs/NETWORK_OPEN_ECP_CONTEXT_V0"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- NETWORK_OPEN_ECP_CONTEXT_V0
product:
- Windows
targetos: Windows
req.typenames: NETWORK_OPEN_ECP_CONTEXT_V0, *PNETWORK_OPEN_ECP_CONTEXT_V0
---

# NETWORK_OPEN_ECP_CONTEXT_V0 structure

## -description

The NETWORK_OPEN_ECP_CONTEXT_V0 structure is used to interpret network extra create parameter (ECP) contexts on files.

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

### -field DUMMYSTRUCTNAME.out

Structure that contains post-create restrictions to apply to a file after it has been opened.

### -field DUMMYSTRUCTNAME.out.Location

A [**NETWORK_OPEN_LOCATION_QUALIFIER**](ne-ntifs-network_open_location_qualifier.md)-typed value that specifies the location restriction to attach to the file.

### -field DUMMYSTRUCTNAME.out.Integrity

This member is currently not implemented and should be ignored.

A [**NETWORK_OPEN_INTEGRITY_QUALIFIER**](ne-ntifs-network_open_integrity_qualifier.md)-typed value that specifies the integrity restriction to attach to the file.

## -remarks

For information about how to use ECPs to associate extra information with a file when the file is created, see [Using Extra Create Parameters with an IRP_MJ_CREATE Operation](https://docs.microsoft.com/windows-hardware/drivers/ifs/using-extra-create-parameters-with-an-irp-mj-create-operation).

The NETWORK_OPEN_ECP_CONTEXT_V0 structure is read-only. You should use it to retrieve information about the network ECP context on a file only. For more information, see [System-Defined ECPs](https://docs.microsoft.com/windows-hardware/drivers/ifs/system-defined-ecps).

If a caller must verify that the file system acknowledged the **NETWORK_OPEN_ECP_CONTEXT_V0** context structure, the caller should call the [**FltIsEcpAcknowledged**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisecpacknowledged) or [**FsRtlIsEcpAcknowledged**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisecpacknowledged) routine on the ECP after the operation is complete.

In most cases, drivers that run on Windows Vista and later versions of Windows use the [**NETWORK_OPEN_ECP_CONTEXT**](ns-ntifs-_network_open_ecp_context.md) structure to interpret network ECP contexts on files. However, drivers that run on Windows 7 and later versions of Windows and that must interpret network ECP contexts on files that reside on Windows Vista must use the **NETWORK_OPEN_ECP_CONTEXT_V0** structure instead.

## -see-also

[**FltIsEcpAcknowledged**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisecpacknowledged)

[**FsRtlIsEcpAcknowledged**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisecpacknowledged)

[**NETWORK_OPEN_ECP_CONTEXT**](ns-ntifs-_network_open_ecp_context.md)

[**NETWORK_OPEN_INTEGRITY_QUALIFIER**](ne-ntifs-network_open_integrity_qualifier.md)

[**NETWORK_OPEN_LOCATION_QUALIFIER**](ne-ntifs-network_open_location_qualifier.md)
