---
UID: NS:bdatypes._BDA_DVBT2_L1_SIGNALLING_DATA
title: "_BDA_DVBT2_L1_SIGNALLING_DATA"
author: windows-driver-content
description: "."
old-location: stream\bda_dvbt2_l1_signalling_data.htm
old-project: stream
ms.assetid: 34BD68C3-446A-4074-8F5C-E670BE09083A
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PBDA_DVBT2_L1_SIGNALLING_DATA, _BDA_DVBT2_L1_SIGNALLING_DATA, PBDA_DVBT2_L1_SIGNALLING_DATA, BDA_DVBT2_L1_SIGNALLING_DATA, PBDA_DVBT2_L1_SIGNALLING_DATA structure pointer [Streaming Media Devices], bdatypes/PBDA_DVBT2_L1_SIGNALLING_DATA, stream.bda_dvbt2_l1_signalling_data, bdatypes/BDA_DVBT2_L1_SIGNALLING_DATA, BDA_DVBT2_L1_SIGNALLING_DATA structure [Streaming Media Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bdatypes.h
apiname:
-	BDA_DVBT2_L1_SIGNALLING_DATA
product: Windows
targetos: Windows
req.typenames: BDA_DVBT2_L1_SIGNALLING_DATA, *PBDA_DVBT2_L1_SIGNALLING_DATA
---

# _BDA_DVBT2_L1_SIGNALLING_DATA structure


## -description





## -syntax


````
typedef struct _BDA_DVBT2_L1_SIGNALLING_DATA {
  BYTE L1Pre_TYPE;
  BYTE L1Pre_BWT_S1_S2;
  BYTE L1Pre_REPETITION_GUARD_PAPR;
  BYTE L1Pre_MOD_COD_FEC;
  BYTE L1Pre_POSTSIZE_INFO_PILOT[5];
  BYTE L1Pre_TX_ID_AVAIL;
  BYTE L1Pre_CELL_ID[2];
  BYTE L1Pre_NETWORK_ID[2];
  BYTE L1Pre_T2SYSTEM_ID[2];
  BYTE L1Pre_NUM_T2_FRAMES;
  BYTE L1Pre_NUM_DATA_REGENFLAG_L1POSTEXT[2];
  BYTE L1Pre_NUMRF_CURRENTRF_RESERVED[2];
  BYTE L1Pre_CRC32[4];
  BYTE L1PostData[MIN_DIMENSION];
} BDA_DVBT2_L1_SIGNALLING_DATA, *PBDA_DVBT2_L1_SIGNALLING_DATA;
````


## -struct-fields




### -field L1Pre_TYPE


### -field L1Pre_BWT_S1_S2


### -field L1Pre_REPETITION_GUARD_PAPR


### -field L1Pre_MOD_COD_FEC


### -field L1Pre_POSTSIZE_INFO_PILOT


### -field L1Pre_TX_ID_AVAIL


### -field L1Pre_CELL_ID


### -field L1Pre_NETWORK_ID


### -field L1Pre_T2SYSTEM_ID


### -field L1Pre_NUM_T2_FRAMES


### -field L1Pre_NUM_DATA_REGENFLAG_L1POSTEXT


### -field L1Pre_NUMRF_CURRENTRF_RESERVED


### -field L1Pre_CRC32


### -field L1PostData

