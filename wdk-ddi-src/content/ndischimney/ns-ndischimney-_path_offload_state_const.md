---
UID: NS:ndischimney._PATH_OFFLOAD_STATE_CONST
title: _PATH_OFFLOAD_STATE_CONST
author: windows-driver-content
description: The PATH_OFFLOAD_STATE_CONST structure contains the constant variables of a path state object.
old-location: netvista\path_offload_state_const.htm
old-project: netvista
ms.assetid: a71f70f6-7731-457b-bd6d-b4a649f76f8b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndischimney/PATH_OFFLOAD_STATE_CONST, *PPATH_OFFLOAD_STATE_CONST, PATH_OFFLOAD_STATE_CONST structure [Network Drivers Starting with Windows Vista], _PATH_OFFLOAD_STATE_CONST, PPATH_OFFLOAD_STATE_CONST structure pointer [Network Drivers Starting with Windows Vista], PPATH_OFFLOAD_STATE_CONST, PATH_OFFLOAD_STATE_CONST, ndischimney/PPATH_OFFLOAD_STATE_CONST, netvista.path_offload_state_const, tcp_chim_struct_4412519c-3610-4f0a-a4c6-400ff661d205.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
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
-	ndischimney.h
apiname: 
-	PATH_OFFLOAD_STATE_CONST
product: Windows
targetos: Windows
req.typenames: PATH_OFFLOAD_STATE_CONST, *PPATH_OFFLOAD_STATE_CONST
---

# _PATH_OFFLOAD_STATE_CONST structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The PATH_OFFLOAD_STATE_CONST structure contains the constant variables of a path state object.


## -syntax


````
typedef struct _PATH_OFFLOAD_STATE_CONST {
  OFFLOAD_STATE_HEADER Header;
  const UCHAR          *SourceAddress;
  const UCHAR          *DestinationAddress;
} PATH_OFFLOAD_STATE_CONST, *PPATH_OFFLOAD_STATE_CONST;
````


## -struct-fields




### -field Header

An 
     <a href="..\ndischimney\ns-ndischimney-_offload_state_header.md">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the PATH_OFFLOAD_STATE_CONST structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.


### -field SourceAddress

A pointer to the source IP address of a TCP connection. If the TCP connection is over IPv4, the
     address is a 4-byte IPv4 address. If the TCP connection is over IPv6, the address is a 16-byte IPv6
     address. The source address bytes are always in network byte order.


### -field DestinationAddress

A pointer to the destination IP address of a TCP connection. If the TCP connection is over IPv4,
     the address is a 4-byte IPv4 address. If the TCP connection is over IPv6, the address is a 16-byte IPv6
     address. The destination address bytes are always in network byte order.


## -remarks


The value of each path constant variable does not change during the life of a TCP connection. Neither
    the host stack nor the offload target changes the values of a path constant variable. When the host stack
    terminates the offload of the path state object by causing NDIS to call the offload target's 
    <mshelp:link keywords="netvista.miniportterminateoffload" tabindex="0"><i>
    MiniportTerminateOffload</i></mshelp:link> function, the offload target does not return the value of the offloaded
    path constant variables to the host stack.

When passed to an offload target, a PATH_OFFLOAD_STATE_CONST structure is associated with an 
    <mshelp:link keywords="netvista.ndis_miniport_offload_block_list" tabindex="0"><b>
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</b></mshelp:link> structure, which contains a header that is formatted as an 
    <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The 
    <b>Revision</b> member of the NDIS_OBJECT_HEADER structure, in this case, specifies the revision number of
    the PATH_OFFLOAD_STATE_CONST structure.



## -see-also

<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>

<a href="..\ndischimney\ns-ndischimney-_path_offload_state_cached.md">PATH_OFFLOAD_STATE_CACHED</a>

<a href="..\ndischimney\ns-ndischimney-_offload_state_header.md">OFFLOAD_STATE_HEADER</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\ndischimney\ns-ndischimney-_path_offload_state_delegated.md">PATH_OFFLOAD_STATE_DELEGATED</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PATH_OFFLOAD_STATE_CONST structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

