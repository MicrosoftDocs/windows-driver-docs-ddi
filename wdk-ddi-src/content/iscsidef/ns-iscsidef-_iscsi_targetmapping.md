---
UID: NS:iscsidef._ISCSI_TargetMapping
title: _ISCSI_TargetMapping (iscsidef.h)
description: The ISCSI_TargetMapping structure maps a collection of logical unit numbers (LUNs) that are locally defined to a group of 64-bit iSCSI logical unit numbers.
old-location: storage\iscsi_targetmapping.htm
tech.root: storage
ms.assetid: 9b8c5024-5d37-4f85-be00-1a60dd9ab323
ms.date: 03/29/2018
keywords: ["_ISCSI_TargetMapping structure"]
ms.keywords: "*PISCSI_TargetMapping, ISCSI_TargetMapping, ISCSI_TargetMapping structure [Storage Devices], PISCSI_TargetMapping, PISCSI_TargetMapping structure pointer [Storage Devices], _ISCSI_TargetMapping, iscsidef/ISCSI_TargetMapping, iscsidef/PISCSI_TargetMapping, storage.iscsi_targetmapping, structs-iSCSI_5512347c-9b89-4d14-9c84-4e7b9191dbfa.xml"
f1_keywords:
 - "iscsidef/ISCSI_TargetMapping"
 - "ISCSI_TargetMapping"
req.header: iscsidef.h
req.include-header: Iscsidef.h
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
- iscsidef.h
api_name:
- ISCSI_TargetMapping
product:
- Windows
targetos: Windows
req.typenames: ISCSI_TargetMapping, *PISCSI_TargetMapping
---

# _ISCSI_TargetMapping structure


## -description


The ISCSI_TargetMapping structure maps a collection of logical unit numbers (LUNs) that are locally defined to a group of 64-bit iSCSI logical unit numbers. 


## -struct-fields




### -field OSBus

The SCSI bus number (which is valid in the local operating system) that the remote target is mapped to. A value of 0xffffffff indicates that the miniport driver can associate any SCSI bus number with the target. 


### -field OSTarget

The SCSI target number (which is valid in the local operating system) that the remote target is mapped to. A value of 0xffffffff indicates that the miniport driver can pick any number to identify the remote target device.


### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods both return this value in their UniqueSessionId parameter. Do not confuse this value with the values in the ISID and TSID members.


### -field LUNCount

The number of LUNs that are associated with the remote target device.


### -field TargetName

A wide character string that indicates the target name. 


### -field FromPersistentLogin

A Boolean value that indicates whether the logon session is persistent. If this member is <b>TRUE</b>, the logon session is persistent and the system creates it automatically when the computer boots up. If this member is <b>FALSE</b>, the logon session is not persistent.


### -field Reserved

Reserved for Microsoft use only.


### -field LUNList

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_lunlist">ISCSI_LUNList</a> structure that holds a list of LUNs that are associated with the target device.


## -remarks



A 64-bit iSCSI LUN by itself does not uniquely identify the logical unit that it represents. However, the combination of an iSCSI LUN and the name of the target that the logical unit belongs to does provide a unique identification for that logical unit that is valid anywhere in the network. 

Management applications can use the ISCSI_TargetMapping structure to specify a local LUN number that can be assigned to the target LUN that the operating system finds during device enumerations.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_lunlist">ISCSI_LUNList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-targetmapping-wmi-class">ISCSI_TargetMapping WMI Class</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>
 

 

