---
UID: NS:iscsimgt._ISCSI_ConnectionStaticInfo
title: _ISCSI_ConnectionStaticInfo (iscsimgt.h)
description: The ISCSI_ConnectionStaticInfo structure contains information about the characteristics of an established connection.
old-location: storage\iscsi_connectionstaticinfo.htm
tech.root: storage
ms.assetid: 14d4464e-d4e8-446c-8822-0b16c984313c
ms.date: 03/29/2018
keywords: ["ISCSI_ConnectionStaticInfo structure"]
ms.keywords: "*PISCSI_ConnectionStaticInfo, ISCSI_ConnectionStaticInfo, ISCSI_ConnectionStaticInfo structure [Storage Devices], PISCSI_ConnectionStaticInfo, PISCSI_ConnectionStaticInfo structure pointer [Storage Devices], _ISCSI_ConnectionStaticInfo, iscsimgt/ISCSI_ConnectionStaticInfo, iscsimgt/PISCSI_ConnectionStaticInfo, storage.iscsi_connectionstaticinfo, structs-iSCSI_ef0dc102-31e4-466e-b094-d4a6b6a01ce6.xml"
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
targetos: Windows
req.typenames: ISCSI_ConnectionStaticInfo, *PISCSI_ConnectionStaticInfo
f1_keywords:
 - _ISCSI_ConnectionStaticInfo
 - iscsimgt/_ISCSI_ConnectionStaticInfo
 - PISCSI_ConnectionStaticInfo
 - iscsimgt/PISCSI_ConnectionStaticInfo
 - ISCSI_ConnectionStaticInfo
 - iscsimgt/ISCSI_ConnectionStaticInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsimgt.h
api_name:
 - ISCSI_ConnectionStaticInfo
---

# _ISCSI_ConnectionStaticInfo structure


## -description

The ISCSI_ConnectionStaticInfo structure contains information about the characteristics of an established connection.

## -struct-fields

### -field UniqueConnectionId

The connection identifier (ID) that the operating system and application software use to uniquely identify the connection. The <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods both return this value in the <i>UniqueConnectionId</i> parameter. Do not confuse this value with the connection ID (CID).

### -field CID

The iSCSI connection ID (CID) for this connection instance. The iSCSI protocol uses this value to identify the connection.

### -field State

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

### -field Protocol

The transport protocol that is used to establish this connection instance. For a list of values that you can assign to this member, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-connection-protocol-type-qualifiers">ISCSI_CONNECTION_PROTOCOL_TYPE_QUALIFIERS</a>.

### -field HeaderIntegrity

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

### -field DataIntegrity

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

### -field Reserved

Reserved for Microsoft use only. You must set this member to 0.

### -field MaxRecvDataSegmentLength

The maximum data payload size, in bytes, that is supported for command or data PDUs within this connection session.

### -field AuthType

The type of authentication that is used to establish a connection. The <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-connectionstaticinfo-wmi-class">ISCSI_ConnectionStaticInfo WMI Class</a>, which is defined in <i>Mgmt.mof</i>, does specify values for this member; but if your software includes <i>Iscsidsc.h</i>, it can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ne-iscsidef-iscsi_auth_types">ISCSI_AUTH_TYPES</a> enumeration to assign values to this member.

### -field LocalAddr

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a> structure that holds the IP address of the local network card that the initiator uses to connect to the network.

### -field LocalPort

The local port number that this connection instance uses.

### -field RemoteAddr

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a> structure that holds the IP address of the remote network card that this connection instance uses.

### -field RemotePort

The remote port number that the initiator used to make the connection.

### -field EstimatedThroughput

The estimated throughput, in bytes per second, of the connection.

### -field MaxDatagramSize

The maximum size, in bytes, of the datagram that the transport supports.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ne-iscsidef-iscsi_auth_types">ISCSI_AUTH_TYPES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-connection-protocol-type-qualifiers">ISCSI_CONNECTION_PROTOCOL_TYPE_QUALIFIERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-connectionstaticinfo-wmi-class">ISCSI_ConnectionStaticInfo WMI Class</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>

