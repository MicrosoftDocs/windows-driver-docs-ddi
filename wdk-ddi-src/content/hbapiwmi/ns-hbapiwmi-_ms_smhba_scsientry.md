---
UID: NS:hbapiwmi._MS_SMHBA_SCSIENTRY
title: _MS_SMHBA_SCSIENTRY (hbapiwmi.h)
description: The MS_SMHBA_SCSIENTRY structure is used to report target LUN mapping information.
old-location: storage\ms_smhba_scsientry.htm
tech.root: storage
ms.assetid: 38779458-a561-4048-86d8-905e4e50095f
ms.date: 03/29/2018
ms.keywords: "*PMS_SMHBA_SCSIENTRY, MS_SMHBA_SCSIENTRY, MS_SMHBA_SCSIENTRY structure [Storage Devices], PMS_SMHBA_SCSIENTRY, PMS_SMHBA_SCSIENTRY structure pointer [Storage Devices], _MS_SMHBA_SCSIENTRY, hbapiwmi/MS_SMHBA_SCSIENTRY, hbapiwmi/PMS_SMHBA_SCSIENTRY, storage.ms_smhba_scsientry, structs-Fibre_95d0f020-6910-4764-9234-181b525abf5b.xml"
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
- hbapiwmi.h
api_name:
- MS_SMHBA_SCSIENTRY
product:
- Windows
targetos: Windows
req.typenames: MS_SMHBA_SCSIENTRY, *PMS_SMHBA_SCSIENTRY
---

# _MS_SMHBA_SCSIENTRY structure


## -description


The MS_SMHBA_SCSIENTRY structure is used to report target LUN mapping information.


## -struct-fields




### -field PortLun

An array of MS_SMHBA_PORTLUN entries.


### -field LUID

The logical unit descriptor for the device that the operating system derives from SCSI inquiry data.


### -field ScsiId

A structure of type HBAScsiID that contains information that uniquely identifies a logical unit to the operating system.

