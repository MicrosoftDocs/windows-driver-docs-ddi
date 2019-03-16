---
UID: NS:iscsimgt._ISCSI_SessionStaticInfo
title: _ISCSI_SessionStaticInfo (iscsimgt.h)
description: The ISCSI_SessionStaticInfo structure provides information about the characteristics of an iSCSI session.
old-location: storage\iscsi_sessionstaticinfo.htm
tech.root: storage
ms.assetid: c652268f-4a31-4ec1-a668-8700cb7f4e1b
ms.date: 03/29/2018
ms.keywords: "*PISCSI_SessionStaticInfo, ISCSI_SessionStaticInfo, ISCSI_SessionStaticInfo structure [Storage Devices], PISCSI_SessionStaticInfo, PISCSI_SessionStaticInfo structure pointer [Storage Devices], _ISCSI_SessionStaticInfo, iscsimgt/ISCSI_SessionStaticInfo, iscsimgt/PISCSI_SessionStaticInfo, storage.iscsi_sessionstaticinfo, structs-iSCSI_94ec0954-b409-4acf-8935-7c8dc6b0d095.xml"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsimgt.h
api_name:
- ISCSI_SessionStaticInfo
product:
- Windows
targetos: Windows
req.typenames: ISCSI_SessionStaticInfo, *PISCSI_SessionStaticInfo
---

# _ISCSI_SessionStaticInfo structure


## -description


The ISCSI_SessionStaticInfo structure provides information about the characteristics of an iSCSI session.


## -struct-fields




### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in their UniqueSessionId parameter. Do not confuse this value with the values in the <b>ISID</b> and <b>TSID</b> members.


### -field InitiatoriSCSIName

A wide character string that specifies the initiator node name.


### -field TargetiSCSIName

A wide character string that specifies the node name of the target.


### -field TSID

An internal value that specifies the portion of the iSCSI session ID that the target provides. The iSCSI protocol uses TSID together with ISID to identify the session. Do not confuse TSID with the session ID that <b>UniqueSessionId</b> specifies.


### -field ISID

An internal value that specifies the portion of the iSCSI session ID that the initiator provides.


### -field InitialR2t

A Boolean value that indicates if the initiator must wait for a ready-to-send (R2T) request before sending data to the target. If this member is <b>TRUE</b>, the initiator must wait for a ready-to-send (R2T) request before sending data to the target. If this member is <b>FALSE</b>, the initiator can send unsolicited data within limits that the value of <b>FirstBurstLength</b> specifies.


### -field ImmediateData

A Boolean value that indicates if the initiator and target have agreed to allow the transmission of immediate data in the session. (<i>Immediate data</i> is data that the initiator piggybacks onto an iSCSI command PDU.) If this member is <b>TRUE</b>, the initiator and target have agreed to allow the transmission of immediate data in this session.


### -field Type

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff561567">ISCSI_SESSION_TYPE_QUALIFIERS</a> enumeration value that specifies the type of logon session.

<table>
<tr>
<th>Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
discoverySession

</td>
<td>
Session is being used only for discovery.

</td>
</tr>
<tr>
<td>
informationtalSession

</td>
<td>
Session is being used for a limited set of SCSI commands.

</td>
</tr>
<tr>
<td>
dataSession

</td>
<td>
Session is being used as a full feature session.

</td>
</tr>
<tr>
<td>
bootSession

</td>
<td>
Session is being used to boot from target.

</td>
</tr>
</table>
 


### -field DataSequenceInOrder

A Boolean value that indicates whether sequences of data PDUs must be transmitted by using continuously increasing offsets, except during error recovery. If this member is <b>TRUE</b>, sequences of data PDUs must be transmitted by using continuously increasing offsets, except during error recovery. If this member is <b>FALSE</b>, sequences of data PDUs can be transmitted in any order. 

The value in <b>DataSequenceInOrder</b> indicates the ordering of the sequences themselves, not the ordering of the data PDUs within each sequence. The <b>DataPduInOrder</b> member indicates the ordering of the data PDUs within each sequence. 


### -field DataPduInOrder

A Boolean value that indicates whether the data PDUs within a sequence of data PDUs must be located at continuously increasing addresses. If this member is <b>TRUE</b>, the data PDUs within a sequence of data PDUs must be located at continuously increasing addresses, with no gaps or overlay between PDUs. If this member is <b>FALSE</b>, the data PDUs within each sequence can be in any order. 


### -field ErrorRecoveryLevel

The level of error recovery that the initiator and the target negotiated. Higher numbers represent more elaborate recovery schemes. Currently, this member must be 0 or ULONG_VALUE_UNKNOWN.


### -field MaxOutstandingR2t

The maximum number of outstanding ready-to-transmit (R2T) requests that are allowed for each task within this session. 


### -field FirstBurstLength

The maximum amount of unsolicited data, in bytes, that you can send within this session. 


### -field MaxBurstLength

The maximum number of bytes that you can send within a single sequence of Data-In or Data-Out PDUs. 


### -field MaxConnections

The maximum number of connections that are allowed within this session.


### -field ConnectionCount

The number of connections that currently belong to this session.


### -field ConnectionsList

A variable length array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561489">ISCSI_ConnectionStaticInfo</a> structures that specifies the static configuration data for each connection that is associated with this session. <b>ConnectionCount</b> indicates the number of elements in the array.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561489">ISCSI_ConnectionStaticInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561598">LOGINSESSIONTYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>
 

 

