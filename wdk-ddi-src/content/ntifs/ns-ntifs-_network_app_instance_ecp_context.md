---
UID: NS:ntifs._NETWORK_APP_INSTANCE_ECP_CONTEXT
title: "_NETWORK_APP_INSTANCE_ECP_CONTEXT"
author: windows-driver-content
description: The NETWORK_APP_INSTANCE_ECP_CONTEXT structure is an Extra Create Parameter (ECP) and contains an application instance identifier to associate with a file.
old-location: ifsk\network_app_instance_ecp_context.htm
old-project: ifsk
ms.assetid: ADB7550F-9191-4EAA-BEBA-0D0D29EC7B03
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNETWORK_APP_INSTANCE_ECP_CONTEXT, ,, A, C, E, I, K, N, NETWORK_APP_INSTANCE_ECP_CONTEXT, NETWORK_APP_INSTANCE_ECP_CONTEXT structure [Installable File System Drivers], O, P, PNETWORK_APP_INSTANCE_ECP_CONTEXT, PNETWORK_APP_INSTANCE_ECP_CONTEXT structure pointer [Installable File System Drivers], R, S, T, W, X, _, _NETWORK_APP_INSTANCE_ECP_CONTEXT, ifsk.network_app_instance_ecp_context, ntifs/NETWORK_APP_INSTANCE_ECP_CONTEXT, ntifs/PNETWORK_APP_INSTANCE_ECP_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available in Windows 8 and later versions of Windows.
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
-	Ntifs.h
apiname:
-	NETWORK_APP_INSTANCE_ECP_CONTEXT
product: Windows
targetos: Windows
req.typenames: NETWORK_APP_INSTANCE_ECP_CONTEXT, *PNETWORK_APP_INSTANCE_ECP_CONTEXT
---

# _NETWORK_APP_INSTANCE_ECP_CONTEXT structure


## -description


The <b>NETWORK_APP_INSTANCE_ECP_CONTEXT</b> structure is an Extra Create Parameter (ECP) and contains an application instance identifier  to associate with a file. This structure is used to identify the files opened for a failover cluster client application when that application resumes access to its files on another node. 


## -syntax


````
typedef struct _NETWORK_APP_INSTANCE_ECP_CONTEXT {
  USHORT Size;
  USHORT Reserved;
  GUID   AppInstanceID;
} NETWORK_APP_INSTANCE_ECP_CONTEXT, *PNETWORK_APP_INSTANCE_ECP_CONTEXT;
````


## -struct-fields




### -field Size

Size of this structure. This member is set to <b>sizeof</b>(NETWORK_APP_INSTANCE_ECP_CONTEXT).


### -field Reserved

Reserved. Must be set to zero.


### -field AppInstanceID

A unique instance identifier for a failover cluster client application. This is a GUID that associates an application  to file opened on a failover cluster node.


## -remarks



When  failover to a secondary node in a server cluster occurs, a cluster client application needs resumed access to the files it first opened on the failed node. The Cluster Client Failover infrastructure prevents sharing violations for the application's files on the failover node by validating its access to those files. Access is granted to the files the on the failover node having the same application instance identifier as the files opened on other node had  prior to failover. The instance identifier is found  in a <b>NETWORK_APP_INSTANCE_ECP_CONTEXT</b> structure in a file's ECP list.

For example, a file system filter driver will allocate a <b>NETWORK_APP_INSTANCE_ECP_CONTEXT</b> with the unique application instance GUID. The context structure is inserted into the ECP list of a file when it is created or opened. The cluster nodes cache the instance identifier from the ECP when processing the network file system create request. On failover, the resuming node can match the application to its set of opened files and grant access.

The <b>NETWORK_APP_INSTANCE_ECP_CONTEXT</b> is identified in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a> by <b>GUID_ECP_NETWORK_APP_INSTANCE</b>. This and other system-defined identifiers are described in <a href="https://msdn.microsoft.com/6acb4be4-a7aa-431d-b2d8-3ef6d41cb4ef">System-Defined ECPs</a>.

For information about how to use ECPs to associate extra information with a file when the file is created, see <a href="https://msdn.microsoft.com/e32aeec6-1a0a-4d21-8358-89d9fc0a15eb">Using Extra Create Parameters with an IRP_MJ_CREATE Operation</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20NETWORK_APP_INSTANCE_ECP_CONTEXT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

