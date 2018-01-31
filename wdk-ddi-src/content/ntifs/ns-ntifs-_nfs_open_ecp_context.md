---
UID: NS:ntifs._NFS_OPEN_ECP_CONTEXT
title: "_NFS_OPEN_ECP_CONTEXT"
author: windows-driver-content
description: The NFS_OPEN_ECP_CONTEXT structure is used by the Network File System (NFS) server to open files in response to client requests.
old-location: ifsk\nfs_open_ecp_context.htm
old-project: ifsk
ms.assetid: f3600dca-d246-41b5-99b4-4054e677b03b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: NFS_OPEN_ECP_CONTEXT structure [Installable File System Drivers], ECP_Structures_d19b2618-0b21-424c-b5bd-abc9b6bdc518.xml, PNFS_OPEN_ECP_CONTEXT structure pointer [Installable File System Drivers], PNFS_OPEN_ECP_CONTEXT, PPNFS_OPEN_ECP_CONTEXT structure pointer [Installable File System Drivers], ifsk.nfs_open_ecp_context, PPNFS_OPEN_ECP_CONTEXT, _NFS_OPEN_ECP_CONTEXT, *PNFS_OPEN_ECP_CONTEXT, ntifs/NFS_OPEN_ECP_CONTEXT, ntifs/PPNFS_OPEN_ECP_CONTEXT, NFS_OPEN_ECP_CONTEXT, ntifs/PNFS_OPEN_ECP_CONTEXT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	NFS_OPEN_ECP_CONTEXT
product: Windows
targetos: Windows
req.typenames: PPNFS_OPEN_ECP_CONTEXT, NFS_OPEN_ECP_CONTEXT, *PNFS_OPEN_ECP_CONTEXT
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




#### - ExportAlias

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that supplies the export alias (share name) for the NFS server that contains the files to be opened. This member is a hint and can be a name, <b>NULL</b>, or a zero-length string. 


#### - ClientSocketAddress

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570825">SOCKADDR_STORAGE</a> structure that specifies the transport address of the client computer. This client originates the open file request. 


## -remarks


The file-system stack can determine whether NFS_OPEN_ECP_CONTEXT is attached to the create file request. The file-system stack can then use the information in NFS_OPEN_ECP_CONTEXT to determine the client that requested that the file be opened and why it was requested. For information about how to retrieve the NFS_OPEN_ECP_CONTEXT extra information that is attached to a create file request, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/using-ecps-to-process-irp-mj-create-operations-in-a-file-system-filter">Retrieving ECPs</a>. 

The NFS_OPEN_ECP_CONTEXT structure is read-only. You should use it to retrieve information about the open file ECP only. For more information about this issue, see <a href="https://msdn.microsoft.com/6acb4be4-a7aa-431d-b2d8-3ef6d41cb4ef">System-Defined ECPs</a>.



## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570825">SOCKADDR_STORAGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20NFS_OPEN_ECP_CONTEXT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

