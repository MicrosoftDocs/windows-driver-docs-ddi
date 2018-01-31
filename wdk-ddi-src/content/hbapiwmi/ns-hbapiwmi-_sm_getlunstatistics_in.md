---
UID: NS:hbapiwmi._SM_GetLUNStatistics_IN
title: "_SM_GetLUNStatistics_IN"
author: windows-driver-content
description: The SM_GetLUNStatistics_IN structure is used to provide input parameters to the SM_GetLUNStatistics_IN method.
old-location: storage\sm_getlunstatistics_in.htm
old-project: storage
ms.assetid: c551a376-2148-4fc4-ba4e-9c1ce1eea1d8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSM_GetLUNStatistics_IN, _SM_GetLUNStatistics_IN, hbapiwmi/PSM_GetLUNStatistics_IN, SM_GetLUNStatistics_IN structure [Storage Devices], *PSM_GetLUNStatistics_IN, SM_GetLUNStatistics_IN, structs-Fibre_537f91a2-0183-4e6d-a3ef-22474349e6e7.xml, PSM_GetLUNStatistics_IN structure pointer [Storage Devices], hbapiwmi/SM_GetLUNStatistics_IN, storage.sm_getlunstatistics_in
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	SM_GetLUNStatistics_IN
product: Windows
targetos: Windows
req.typenames: SM_GetLUNStatistics_IN, *PSM_GetLUNStatistics_IN
---

# _SM_GetLUNStatistics_IN structure


## -description


The SM_GetLUNStatistics_IN structure is used to provide input parameters to the SM_GetLUNStatistics_IN method.


## -syntax


````
typedef struct _SM_GetLUNStatistics_IN {
  HBAScsiID Lunit;
} SM_GetLUNStatistics_IN, *PSM_GetLUNStatistics_IN;
````


## -struct-fields




#### - Lunit

A structure of type <a href="..\hbaapi\ns-hbaapi-hba_scsiid.md">HBA_ScsiId</a> that contains information that is used by the operating system to identify a SCSI logical unit.


## -remarks


When the WMI tool suite compiles the MS_SM_TargetInformationMethods WMI class, it generates a declaration of the SM_GetLUNStatistics_IN structure in <i>Hbapiwmi.h</i>.


