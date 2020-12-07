---
UID: NS:hbapiwmi._MS_SMHBA_SASPHYSTATISTICS
title: _MS_SMHBA_SASPHYSTATISTICS (hbapiwmi.h)
description: The MS_SMHBA_SASPHYSTATISTICS structure reports the traffic statistics for a SAS physical link.
old-location: storage\ms_smhba_sasphystatistics.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["MS_SMHBA_SASPHYSTATISTICS structure"]
ms.keywords: "*PMS_SMHBA_SASPHYSTATISTICS, MS_SMHBA_SASPHYSTATISTICS, MS_SMHBA_SASPHYSTATISTICS structure [Storage Devices], PMS_SMHBA_SASPHYSTATISTICS, PMS_SMHBA_SASPHYSTATISTICS structure pointer [Storage Devices], _MS_SMHBA_SASPHYSTATISTICS, hbapiwmi/MS_SMHBA_SASPHYSTATISTICS, hbapiwmi/PMS_SMHBA_SASPHYSTATISTICS, storage.ms_smhba_sasphystatistics, structs-Fibre_7059d482-c967-4f18-8c03-b113573cff2f.xml"
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
targetos: Windows
req.typenames: MS_SMHBA_SASPHYSTATISTICS, *PMS_SMHBA_SASPHYSTATISTICS
f1_keywords:
 - _MS_SMHBA_SASPHYSTATISTICS
 - hbapiwmi/_MS_SMHBA_SASPHYSTATISTICS
 - PMS_SMHBA_SASPHYSTATISTICS
 - hbapiwmi/PMS_SMHBA_SASPHYSTATISTICS
 - MS_SMHBA_SASPHYSTATISTICS
 - hbapiwmi/MS_SMHBA_SASPHYSTATISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - MS_SMHBA_SASPHYSTATISTICS
---

# _MS_SMHBA_SASPHYSTATISTICS structure


## -description

The MS_SMHBA_SASPHYSTATISTICS structure reports the traffic statistics for a SAS physical link.

## -struct-fields

### -field SecondsSinceLastReset

The number of seconds since the statistics were last reset.

### -field TxFrames

The number of transmitted SAS frames across all protocols and classes.

### -field TxWords

The number of transmitted SAS words across all protocols and classes.

### -field RxFrames

The number of received SAS frames across all protocols and classes.

### -field RxWords

The number of received SAS words across all protocols and classes.

### -field InvalidDwordCount

The number of invalid DWORDs.

### -field RunningDisparityErrorCount

The number of disparity error counts.

### -field LossofDwordSyncCount

The loss of synchronization count.

### -field PhyResetProblemCount

A count of the number of physical link reset problems.

