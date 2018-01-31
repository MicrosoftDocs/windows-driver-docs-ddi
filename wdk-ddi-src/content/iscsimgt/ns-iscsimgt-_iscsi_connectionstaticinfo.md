---
UID: NS:iscsimgt._ISCSI_ConnectionStaticInfo
title: "_ISCSI_ConnectionStaticInfo"
author: windows-driver-content
description: The ISCSI_ConnectionStaticInfo structure contains information about the characteristics of an established connection.
old-location: storage\iscsi_connectionstaticinfo.htm
old-project: storage
ms.assetid: 14d4464e-d4e8-446c-8822-0b16c984313c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: iscsimgt/ISCSI_ConnectionStaticInfo, ISCSI_ConnectionStaticInfo structure [Storage Devices], structs-iSCSI_ef0dc102-31e4-466e-b094-d4a6b6a01ce6.xml, ISCSI_ConnectionStaticInfo, storage.iscsi_connectionstaticinfo, *PISCSI_ConnectionStaticInfo, PISCSI_ConnectionStaticInfo, iscsimgt/PISCSI_ConnectionStaticInfo, _ISCSI_ConnectionStaticInfo, PISCSI_ConnectionStaticInfo structure pointer [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
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
-	iscsimgt.h
apiname:
-	ISCSI_ConnectionStaticInfo
product: Windows
targetos: Windows
req.typenames: ISCSI_ConnectionStaticInfo, *PISCSI_ConnectionStaticInfo
---

# _ISCSI_ConnectionStaticInfo structure


## -description


The ISCSI_ConnectionStaticInfo structure contains information about the characteristics of an established connection.


## -syntax


````
typedef struct _ISCSI_ConnectionStaticInfo {
  ULONGLONG        UniqueConnectionId;
  USHORT           CID;
  UCHAR            State;
  UCHAR            Protocol;
  UCHAR            HeaderIntegrity;
  UCHAR            DataIntegrity;
  USHORT           Reserved;
  ULONG            MaxRecvDataSegmentLength;
  ULONG            AuthType;
  ISCSI_IP_Address LocalAddr;
  ULONG            LocalPort;
  ISCSI_IP_Address RemoteAddr;
  ULONG            RemotePort;
  ULONGLONG        EstimatedThroughput;
  ULONG            MaxDatagramSize;
} ISCSI_ConnectionStaticInfo, *PISCSI_ConnectionStaticInfo;
````


## -struct-fields




#### - UniqueConnectionId

The connection identifier (ID) that the operating system and application software use to uniquely identify the connection. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in the <i>UniqueConnectionId</i> parameter. Do not confuse this value with the connection ID (CID).


#### - CID

The iSCSI connection ID (CID) for this connection instance. The iSCSI protocol uses this value to identify the connection.


#### - State

The type of connection state. This member can have the following symbolic constant values, which are defined in <i>Iscsimgt.h</i>.
<table>
<tr>
<th>State</th>
<th>Meaning</th>
</tr>
<tr>
<td>
login

</td>
<td>
The TCP connection has been established, but the target still has not sent a valid logon response with the final bit set. 

</td>
</tr>
<tr>
<td>
full

</td>
<td>
The target has sent a valid logon response with the final bit set, and the connection is in the full feature phase. The initiator can send SCSI commands and data to targets. 

</td>
</tr>
<tr>
<td>
logout

</td>
<td>
The initiator has sent a valid logoff command, but the connection has not yet been closed.

</td>
</tr>
</table> 


#### - Protocol

The transport protocol that is used to establish this connection instance. For a list of values that you can assign to this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561494">ISCSI_CONNECTION_PROTOCOL_TYPE_QUALIFIERS</a>.


#### - HeaderIntegrity

The name of the iSCSI header digest scheme that is associated with this connection session. This member can have the following symbolic constant values, which are defined in <i>Iscsimgt.h</i>.
<table>
<tr>
<th>HeaderIntegrity</th>
<th>Meaning</th>
</tr>
<tr>
<td>
None

</td>
<td>
The session is not using a header digest. 

</td>
</tr>
<tr>
<td>
crc32c

</td>
<td>
The session is using a 32-bit CRC digest.

</td>
</tr>
</table> 


#### - DataIntegrity

The name of the iSCSI data digest scheme that is associated with this connection session. This member can have the following symbolic constant values, which are defined in <i>Iscsimgt.h</i>.
<table>
<tr>
<th>HeaderIntegrity</th>
<th>Meaning</th>
</tr>
<tr>
<td>
None

</td>
<td>
The session is not using a data digest. 

</td>
</tr>
<tr>
<td>
crc32c

</td>
<td>
The session is using a 32-bit CRC digest.

</td>
</tr>
</table> 


#### - Reserved

Reserved for Microsoft use only. You must set this member to 0.


#### - MaxRecvDataSegmentLength

The maximum data payload size, in bytes, that is supported for command or data PDUs within this connection session.


#### - AuthType

The type of authentication that is used to establish a connection. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561490">ISCSI_ConnectionStaticInfo WMI Class</a>, which is defined in <i>Mgmt.mof</i>, does specify values for this member; but if your software includes <i>Iscsidsc.h</i>, it can use the <a href="..\iscsidef\ne-iscsidef-piscsi_auth_types.md">ISCSI_AUTH_TYPES</a> enumeration to assign values to this member.


#### - LocalAddr

A <a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a> structure that holds the IP address of the local network card that the initiator uses to connect to the network.


#### - LocalPort

The local port number that this connection instance uses.


#### - RemoteAddr

A <a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a> structure that holds the IP address of the remote network card that this connection instance uses.


#### - RemotePort

The remote port number that the initiator used to make the connection.


#### - EstimatedThroughput

The estimated throughput, in bytes per second, of the connection.


#### - MaxDatagramSize

The maximum size, in bytes, of the datagram that the transport supports.


## -see-also

<a href="..\iscsidef\ne-iscsidef-piscsi_auth_types.md">ISCSI_AUTH_TYPES</a>

<a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561494">ISCSI_CONNECTION_PROTOCOL_TYPE_QUALIFIERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561490">ISCSI_ConnectionStaticInfo WMI Class</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_ConnectionStaticInfo structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

