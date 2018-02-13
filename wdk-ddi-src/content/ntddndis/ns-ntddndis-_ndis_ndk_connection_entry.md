---
UID: NS:ntddndis._NDIS_NDK_CONNECTION_ENTRY
title: "_NDIS_NDK_CONNECTION_ENTRY"
author: windows-driver-content
description: The NDIS_NDK_CONNECTION_ENTRY structure specifies a connection entry for an active NDK connection on a miniport adapter.
old-location: netvista\ndis_ndk_connection_entry.htm
old-project: netvista
ms.assetid: 58BA2AE1-9F48-4B3B-A545-EECC9B3E858C
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndis_ndk_connection_entry, PNDIS_NDK_CONNECTION_ENTRY, PNDIS_NDK_CONNECTION_ENTRY structure pointer [Network Drivers Starting with Windows Vista], NDIS_NDK_CONNECTION_ENTRY structure [Network Drivers Starting with Windows Vista], _NDIS_NDK_CONNECTION_ENTRY, ntddndis/NDIS_NDK_CONNECTION_ENTRY, NDIS_NDK_CONNECTION_ENTRY, ntddndis/PNDIS_NDK_CONNECTION_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddndis.h
apiname:
-	NDIS_NDK_CONNECTION_ENTRY
product: Windows
targetos: Windows
req.typenames: NDIS_NDK_CONNECTION_ENTRY
---

# _NDIS_NDK_CONNECTION_ENTRY structure


## -description


The <b>NDIS_NDK_CONNECTION_ENTRY</b> structure specifies a connection entry for an active NDK connection on a miniport adapter.


## -syntax


````
typedef struct _NDIS_NDK_CONNECTION_ENTRY {
  SOCKADDR_INET Local;
  SOCKADDR_INET Remote;
  BOOLEAN       UserModeOwner;
  ULONG         OwnerPid;
} NDIS_NDK_CONNECTION_ENTRY, *PNDIS_NDK_CONNECTION_ENTRY;
````


## -struct-fields




### -field Local

The local IP address and port.


### -field Remote

The remote IP address and port.


### -field UserModeOwner

A BOOLEAN value that is TRUE if the connection is an NDS user-mode connection, or FALSE if it is an NDK kernel-mode connection.


### -field OwnerPid

A process identifier for an NDS user-mode connection.


## -remarks



The NDIS_NDK_CONNECTION_ENTRY structure is used in the <a href="..\ntddndis\ns-ntddndis-_ndis_ndk_connections.md">NDIS_NDK_CONNECTIONS</a> structure to specify an array of connections.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_ndk_connections.md">NDIS_NDK_CONNECTIONS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NDK_CONNECTION_ENTRY structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

