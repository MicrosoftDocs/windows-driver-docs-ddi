---
UID: NS:ndischimney._TCP_OFFLOAD_STATE_CONST
title: "_TCP_OFFLOAD_STATE_CONST"
author: windows-driver-content
description: The TCP_OFFLOAD_STATE_CONST structure contains the constant variables of a TCP connection state object.
old-location: netvista\tcp_offload_state_const.htm
old-project: netvista
ms.assetid: 3e80f963-a494-475a-a246-abe5674dbcb6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndischimney/TCP_OFFLOAD_STATE_CONST, TCP_OFFLOAD_STATE_CONST, PTCP_OFFLOAD_STATE_CONST, TCP_OFFLOAD_STATE_CONST structure [Network Drivers Starting with Windows Vista], PTCP_OFFLOAD_STATE_CONST structure pointer [Network Drivers Starting with Windows Vista], *PTCP_OFFLOAD_STATE_CONST, ndischimney/PTCP_OFFLOAD_STATE_CONST, netvista.tcp_offload_state_const, tcp_chim_struct_d6f90719-24f7-49d1-9253-5d5db776f192.xml, _TCP_OFFLOAD_STATE_CONST
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
-	TCP_OFFLOAD_STATE_CONST
product: Windows
targetos: Windows
req.typenames: "*PTCP_OFFLOAD_STATE_CONST, TCP_OFFLOAD_STATE_CONST"
---

# _TCP_OFFLOAD_STATE_CONST structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The TCP_OFFLOAD_STATE_CONST structure contains the constant variables of a TCP connection state
  object.


## -syntax


````
typedef struct _TCP_OFFLOAD_STATE_CONST {
  OFFLOAD_STATE_HEADER Header;
  USHORT               Flags;
  USHORT               RemotePort;
  USHORT               LocalPort;
  UCHAR                SndWindScale  :4;
  UCHAR                RcvWindScale  :4;
  USHORT               RemoteMss;
  ULONG                HashValue;
} TCP_OFFLOAD_STATE_CONST, *PTCP_OFFLOAD_STATE_CONST;
````


## -struct-fields




### -field Header

An 
     <a href="..\ndischimney\ns-ndischimney-_offload_state_header.md">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the TCP_OFFLOAD_STATE_CONST structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.


### -field Flags

A bitmask that can be set to zero or any of the following flags, combined with bitwise OR:
     





#### TCP_FLAG_TIMESTAMP_ENABLED

The host stack sets this flag to enable the TCP timestamp option on the connection. (For more
       information about the TCP timestamp option, see RFC 1323.) When this option is enabled, the offload
       target must place a timestamp in each TCP segment that it sends. The host stack clears this flag to
       disable the TCP timestamp option on the connection.



#### TCP_FLAG_SACK_ENABLED

The host stack sets this flag to enable selective acknowledgments (SACKs) on the connection.
       (For more information about the SACKs, see RFC 2018.) When this option is enabled, the offload target
       sends and receives SACK blocks over the TCP connection. The host stack clears this flag to disable
       SACKs on the connection.



#### TCP_FLAG_WINDOW_SCALING_ENABLED

The host stack sets this flag to cause the offload target to use scale factors (SndWindScale and
       RcvWindScale) to compute send and receive windows for the connection. (For more information about
       window scale factors, see RFCs 2883 and 3517.) The host stack clears this flag to disable this
       option.


### -field RemotePort

The destination port number (see RFC 793).


### -field LocalPort

The source port number (see RFC 793).


### -field SndWindScale

The send window scale factor (see RFC 1323).


### -field RcvWindScale

The receive window scale factor (see RFC 1323).


### -field RemoteMss

The initial maximum segment size (MSS) advertised by the remote endpoint during TCP connection
     setup. (For more information about MSS, see RFC 2581.)


### -field HashValue

A 32-bit hash value that the offload target uses for 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/receive-side-scaling-on-an-offloaded-tcp-connection">receive side
     scaling (RSS)</a> processing on the TCP connection if the offload target supports RSS.


## -remarks



The value of each TCP constant variable does not change during the life of a TCP connection. Neither
    the host stack nor the offload target changes the values of a TCP constant variable. When the host stack
    terminates the offload of the TCP connection state object by causing NDIS to call the offload target's 
    <a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">
    MiniportTerminateOffload</a> function, the offload target does not return the value of the offloaded
    TCP constant variables to the host stack.

When passed to an offload target, a TCP_OFFLOAD_STATE_CONST structure is associated with an 
    <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which contains a header that is formatted as an 
    <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The 
    <b>Revision</b> member of the NDIS_OBJECT_HEADER structure, in this case, specifies the revision number of
    the TCP_OFFLOAD_STATE_CONST structure.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>



<a href="..\ndischimney\ns-ndischimney-_tcp_offload_state_cached.md">TCP_OFFLOAD_STATE_CACHED</a>



<a href="..\ndischimney\ns-ndischimney-_tcp_offload_state_delegated.md">TCP_OFFLOAD_STATE_DELEGATED</a>



<a href="..\ndischimney\ns-ndischimney-_offload_state_header.md">OFFLOAD_STATE_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TCP_OFFLOAD_STATE_CONST structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

