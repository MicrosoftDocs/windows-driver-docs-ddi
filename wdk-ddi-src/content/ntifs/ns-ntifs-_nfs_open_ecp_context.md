---
UID: NS:ntifs._NFS_OPEN_ECP_CONTEXT
title: "_NFS_OPEN_ECP_CONTEXT"
author: windows-driver-content
description: The NFS_OPEN_ECP_CONTEXT structure is used by the Network File System (NFS) server to open files in response to client requests.
old-location: ifsk\nfs_open_ecp_context.htm
old-project: ifsk
ms.assetid: f3600dca-d246-41b5-99b4-4054e677b03b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNFS_OPEN_ECP_CONTEXT, ECP_Structures_d19b2618-0b21-424c-b5bd-abc9b6bdc518.xml, NFS_OPEN_ECP_CONTEXT, NFS_OPEN_ECP_CONTEXT structure [Installable File System Drivers], PNFS_OPEN_ECP_CONTEXT, PNFS_OPEN_ECP_CONTEXT structure pointer [Installable File System Drivers], PPNFS_OPEN_ECP_CONTEXT, PPNFS_OPEN_ECP_CONTEXT structure pointer [Installable File System Drivers], _NFS_OPEN_ECP_CONTEXT, ifsk.nfs_open_ecp_context, ntifs/NFS_OPEN_ECP_CONTEXT, ntifs/PNFS_OPEN_ECP_CONTEXT, ntifs/PPNFS_OPEN_ECP_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	NFS_OPEN_ECP_CONTEXT
product: Windows
targetos: Windows
req.typenames: NFS_OPEN_ECP_CONTEXT, *PNFS_OPEN_ECP_CONTEXT, PPNFS_OPEN_ECP_CONTEXT
---

# _NFS_OPEN_ECP_CONTEXT structure


## -description


The NFS_OPEN_ECP_CONTEXT structure is used by the Network File System (NFS) server to open files in response to client requests. 


## -syntax


````
typedef struct _NFS_OPEN_ECP_CONTEXT {
  PUNICODE_STRING       ExportAlias;
  PSOCKADDR_STORAGE_NFS ClientSocketAddress;
} NFS_OPEN_ECP_CONTEXT, *PNFS_OPEN_ECP_CONTEXT, **PPNFS_OPEN_ECP_CONTEXT;
````


## -struct-fields




### -field ExportAlias

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that supplies the export alias (share name) for the NFS server that contains the files to be opened. This member is a hint and can be a name, <b>NULL</b>, or a zero-length string. 


### -field ClientSocketAddress

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570825">SOCKADDR_STORAGE</a> structure that specifies the transport address of the client computer. This client originates the open file request. 


## -remarks



The file-system stack can determine whether NFS_OPEN_ECP_CONTEXT is attached to the create file request. The file-system stack can then use the information in NFS_OPEN_ECP_CONTEXT to determine the client that requested that the file be opened and why it was requested. For information about how to retrieve the NFS_OPEN_ECP_CONTEXT extra information that is attached to a create file request, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/using-ecps-to-process-irp-mj-create-operations-in-a-file-system-filter">Retrieving ECPs</a>. 

The NFS_OPEN_ECP_CONTEXT structure is read-only. You should use it to retrieve information about the open file ECP only. For more information about this issue, see <a href="https://msdn.microsoft.com/6acb4be4-a7aa-431d-b2d8-3ef6d41cb4ef">System-Defined ECPs</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570825">SOCKADDR_STORAGE</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 


