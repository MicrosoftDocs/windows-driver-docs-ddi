---
UID: NS:iscsidef._ISCSI_LUNList
title: _ISCSI_LUNList (iscsidef.h)
description: The ISCSI_LUNList structure defines a mapping between the LUN number that is used by the operating system and the LUN number that is configured in the iSCSI target.
old-location: storage\iscsi_lunlist.htm
tech.root: storage
ms.assetid: 1c477f38-c24f-45df-ab02-62ee47c0957b
ms.date: 03/29/2018
keywords: ["_ISCSI_LUNList structure"]
ms.keywords: "*PISCSI_LUNList, ISCSI_LUNList, ISCSI_LUNList structure [Storage Devices], PISCSI_LUNList, PISCSI_LUNList structure pointer [Storage Devices], _ISCSI_LUNList, iscsidef/ISCSI_LUNList, iscsidef/PISCSI_LUNList, storage.iscsi_lunlist, structs-iSCSI_f6a29259-8905-438e-ba9f-1055026d7bf6.xml"
f1_keywords:
 - "iscsidef/ISCSI_LUNList"
 - "ISCSI_LUNList"
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
- ISCSI_LUNList
product:
- Windows
targetos: Windows
req.typenames: ISCSI_LUNList, *PISCSI_LUNList
---

# _ISCSI_LUNList structure


## -description


The ISCSI_LUNList structure defines a mapping between the LUN number that is used by the operating system and the LUN number that is configured in the iSCSI target.


## -struct-fields




### -field TargetLUN

A LUN that is globally valid anywhere in the network.


### -field OSLUN

The SCSI LUN (which is valid in the local operating system) that the remote LUN is mapped to.


### -field Reserved

Reserved for Microsoft use only. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-lunlist-wmi-class">ISCSI_LUNList WMI Class</a>
 

 

