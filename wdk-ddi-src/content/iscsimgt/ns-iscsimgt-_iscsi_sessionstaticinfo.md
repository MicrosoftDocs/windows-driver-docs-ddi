---
UID: NS:iscsimgt._ISCSI_SessionStaticInfo
title: "_ISCSI_SessionStaticInfo"
author: windows-driver-content
description: The ISCSI_SessionStaticInfo structure provides information about the characteristics of an iSCSI session.
old-location: storage\iscsi_sessionstaticinfo.htm
old-project: storage
ms.assetid: c652268f-4a31-4ec1-a668-8700cb7f4e1b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PISCSI_SessionStaticInfo, ,, C, I, ISCSI_SessionStaticInfo, ISCSI_SessionStaticInfo structure [Storage Devices], P, PISCSI_SessionStaticInfo, PISCSI_SessionStaticInfo structure pointer [Storage Devices], S, _, _ISCSI_SessionStaticInfo, a, c, e, f, i, iscsimgt/ISCSI_SessionStaticInfo, iscsimgt/PISCSI_SessionStaticInfo, n, o, s, storage.iscsi_sessionstaticinfo, structs-iSCSI_94ec0954-b409-4acf-8935-7c8dc6b0d095.xml, t"
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
-	ISCSI_SessionStaticInfo
product: Windows
targetos: Windows
req.typenames: ISCSI_SessionStaticInfo, *PISCSI_SessionStaticInfo
---

# _ISCSI_SessionStaticInfo structure


## -description


The ISCSI_SessionStaticInfo structure provides information about the characteristics of an iSCSI session.


## -syntax


````
typedef struct _ISCSI_SessionStaticInfo {
  ULONGLONG                  UniqueSessionId;
  WCHAR                      InitiatoriSCSIName[223 + 1];
  WCHAR                      TargetiSCSIName[223 + 1];
  USHORT                     TSID;
  UCHAR                      ISID[6];
  BOOLEAN                    InitialR2t;
  BOOLEAN                    ImmediateData;
  UCHAR                      Type;
  BOOLEAN                    DataSequenceInOrder;
  BOOLEAN                    DataPduInOrder;
  UCHAR                      ErrorRecoveryLevel;
  ULONG                      MaxOutstandingR2t;
  ULONG                      FirstBurstLength;
  ULONG                      MaxBurstLength;
  ULONG                      MaxConnections;
  USHORT                     ConnectionCount;
  ISCSI_ConnectionStaticInfo ConnectionsList[1];
} ISCSI_SessionStaticInfo, *PISCSI_SessionStaticInfo;
````


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

A variable length array of <a href="..\iscsimgt\ns-iscsimgt-_iscsi_connectionstaticinfo.md">ISCSI_ConnectionStaticInfo</a> structures that specifies the static configuration data for each connection that is associated with this session. <b>ConnectionCount</b> indicates the number of elements in the array.


## -see-also

<a href="..\iscsiop\ne-iscsiop-ploginsessiontype.md">LOGINSESSIONTYPE</a>



<a href="..\iscsimgt\ns-iscsimgt-_iscsi_connectionstaticinfo.md">ISCSI_ConnectionStaticInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_SessionStaticInfo structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

