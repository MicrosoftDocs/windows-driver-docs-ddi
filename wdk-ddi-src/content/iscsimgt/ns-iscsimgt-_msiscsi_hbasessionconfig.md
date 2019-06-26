---
UID: NS:iscsimgt._MSiSCSI_HBASessionConfig
title: _MSiSCSI_HBASessionConfig (iscsimgt.h)
description: The MSiSCSI_HBASessionConfig structure contains the default logon characteristics that a particular instance of a storage miniport driver uses to create a logon session with a target device.
old-location: storage\msiscsi_hbasessionconfig.htm
tech.root: storage
ms.assetid: a97f39b7-9356-45f1-b0a2-bd18eb4c7467
ms.date: 03/29/2018
ms.keywords: "*PMSiSCSI_HBASessionConfig, MSiSCSI_HBASessionConfig, MSiSCSI_HBASessionConfig structure [Storage Devices], PMSiSCSI_HBASessionConfig, PMSiSCSI_HBASessionConfig structure pointer [Storage Devices], _MSiSCSI_HBASessionConfig, iscsimgt/MSiSCSI_HBASessionConfig, iscsimgt/PMSiSCSI_HBASessionConfig, storage.msiscsi_hbasessionconfig, structs-iSCSI_e8f9731d-11fb-42e1-90a0-09e3e6597ebe.xml"
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
- MSiSCSI_HBASessionConfig
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_HBASessionConfig, *PMSiSCSI_HBASessionConfig
---

# _MSiSCSI_HBASessionConfig structure


## -description


The MSiSCSI_HBASessionConfig structure contains the default logon characteristics that a particular instance of a storage miniport driver uses to create a logon session with a target device. 


## -struct-fields




### -field InitialR2T

A Boolean value that indicates if the HBA initiator requests permission from the target to transmit unsolicited SCSI data whenever it establishes a new session. If this member is <b>TRUE</b>, the HBA initiator requests permission from the target to transmit unsolicited SCSI data whenever it establishes a new session. By default, the initiator does not transmit SCSI data until the target solicits the data by sending a ready-to-transmit (R2T) request, with a buffer offset of 0 and a desired transfer length equal to the minimum of the first burst size and the expected data transfer. 

If <b>InitialR2T</b> is <b>TRUE</b>, the initiator sends a protocol data unit (PDU) to the target with the string "No" in the InitialR2T key of the PDU. The target must respond by sending a PDU to the initiator with the string "No" in the InitialR2T key of the PDU. Both initiator and target must agree before unsolicited data transmission is allowed. Therefore, even if you set <b>InitialR2T</b> to <b>TRUE</b>, it does not guarantee that the initiator will be able to send unsolicited SCSI data to the target. 

If this member is <b>FALSE</b>, all sessions that the initiator creates follow the default behavior. For more information about the InitialR2T key, see the <i>IP Storage Working Group</i> specification. 


### -field ImmediateData

A Boolean value that indicates if the initiator requests permission from the target to transmit immediate data whenever it establishes a new session. If this member is <b>TRUE</b>, the initiator requests permission from the target to transmit immediate data whenever it establishes a new session. (<i>Immediate data</i> is data that the initiator piggybacks onto an iSCSI command PDU.) 

The session's policy with regard to immediate data is determined by a negotiation between the initiator and the target. For more information about how the values in <b>ImmediateData</b> and <b>InitialR2T</b> affect the negotiation, see the <i>IP Storage Working Group</i> specification.


### -field MaxRecvDataSegmentLength

The maximum length, in bytes, of a PDU data segment.


### -field MaxBurstLength

The maximum length, in bytes, of the SCSI data payload in a sequence of input (Data-In) PDUs or solicited output (Data-Out) PDUs.


### -field FirstBurstLength

The maximum amount, in bytes, of unsolicited data that an initiator can send to a target during the execution of a single SCSI command. This amount includes the immediate data, if any, and the sequence of unsolicited Data-Out PDUs, if any, that follow the command.


### -field MaxOutstandingR2T

The maximum number of outstanding R2T requests for each task, excluding the first R2T that initiates the task. An R2T is considered <i>outstanding</i> until the last data PDU (with the F bit set to 1) is transferred, or until a sequence reception time-out occurs for that PDU data sequence.


## -remarks



It is optional that you implement this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-hbasessionconfig-wmi-class">MSiSCSI_HBASessionConfig WMI Class</a>
 

 

