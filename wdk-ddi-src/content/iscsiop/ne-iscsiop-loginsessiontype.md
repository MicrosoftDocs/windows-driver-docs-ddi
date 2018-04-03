---
UID: NE:iscsiop.LOGINSESSIONTYPE
title: LOGINSESSIONTYPE
author: windows-driver-content
description: The LOGINSESSIONTYPE enumeration indicates the type of logon session.
old-location: storage\loginsessiontype.htm
old-project: storage
ms.assetid: 838c2371-c1f3-4415-a624-fab1d8c15d0d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PLOGINSESSIONTYPE, ISCSI_LOGINTARGET_DATA, ISCSI_LOGINTARGET_DISCOVERY, ISCSI_LOGINTARGET_INFORMATIONAL, LOGINSESSIONTYPE, LOGINSESSIONTYPE enumeration [Storage Devices], PLOGINSESSIONTYPE, PLOGINSESSIONTYPE enumeration pointer [Storage Devices], iscsiop/ISCSI_LOGINTARGET_DATA, iscsiop/ISCSI_LOGINTARGET_DISCOVERY, iscsiop/ISCSI_LOGINTARGET_INFORMATIONAL, iscsiop/LOGINSESSIONTYPE, iscsiop/PLOGINSESSIONTYPE, storage.loginsessiontype, structs-iSCSI_4af9bc0f-391e-442a-9d45-6819d130cfc0.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	LOGINSESSIONTYPE
product:
- Windows
targetos: Windows
req.typenames: LOGINSESSIONTYPE, *PLOGINSESSIONTYPE
---

# LOGINSESSIONTYPE enumeration


## -description


The LOGINSESSIONTYPE enumeration indicates the type of logon session.


## -enum-fields




### -field ISCSI_LOGINTARGET_DISCOVERY

The logon session is for discovery only. Initiators use this type of session to discover targets with the <b>SendTargets</b> command. The initiator must already have access to at least one target IP address and one target port (target portal information).


### -field ISCSI_LOGINTARGET_INFORMATIONAL

The logon session is for informational purposes only. Initiators use this type of session to send SCSI commands that query for information. Management software can use informational sessions to query for information by calling the <b>SendScsiReportLuns</b> and <b>SendScsiReadCapacity</b> user-mode library routines. 

This type of session does not support transmission of user data, and the Plug and Play (PnP) manager does not enumerate target logical units (LUNs) for the storage stack of the initiator node.


### -field ISCSI_LOGINTARGET_DATA

The logon session is full-featured. It reports the target LUNs to the PnP manager on the (local) initiator node for enumeration. After enumerating these LUNs, the operating system can access them for data transfers, just as it would with local LUNs.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>
 

 

