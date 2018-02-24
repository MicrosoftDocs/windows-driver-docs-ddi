---
UID: NE:ntddrilapitypes.RILREMOTEPARTYINFOVALUEPARAM
title: RILREMOTEPARTYINFOVALUEPARAM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilremotepartyinfovalueparam.htm
old-project: netvista
ms.assetid: 2e0d5214-d2ec-4cb4-8437-a9f5605ea85a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILREMOTEPARTYINFOVALUEPARAM enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_RPI_NAME_PRES_IND, ntddrilapitypes/RILREMOTEPARTYINFOVALUEPARAM, RIL_PARAM_RPI_ADDRESS, RIL_PARAM_RPI_DESCRIPTION, ntddrilapitypes/RIL_PARAM_RPI_ADDRESS, RIL_PARAM_RPI_ID, ntddrilapitypes/RIL_PARAM_RPI_ALL, ntddrilapitypes/RIL_PARAM_RPI_SUBADDRESS, RIL_PARAM_RPI_NUM_PRES_IND, ntddrilapitypes/RIL_PARAM_RPI_DESCRIPTION, RILREMOTEPARTYINFOPARAM, ntddrilapitypes/RIL_PARAM_RPI_ID, ntddrilapitypes/RIL_PARAM_RPI_NUM_PRES_IND, RIL_PARAM_RPI_ALL, ntddrilapitypes/RIL_PARAM_RPI_NAME_PRES_IND, RILREMOTEPARTYINFOVALUEPARAM, netvista.rilremotepartyinfovalueparam, RIL_PARAM_RPI_SUBADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILREMOTEPARTYINFOVALUEPARAM
product: Windows
targetos: Windows
req.typenames: RILREMOTEPARTYINFOPARAM, RILREMOTEPARTYINFOVALUEPARAM
---

# RILREMOTEPARTYINFOVALUEPARAM enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILREMOTEPARTYINFOVALUEPARAM { 
  RIL_PARAM_RPI_ADDRESS,
  RIL_PARAM_RPI_SUBADDRESS,
  RIL_PARAM_RPI_DESCRIPTION,
  RIL_PARAM_RPI_NUM_PRES_IND,
  RIL_PARAM_RPI_NAME_PRES_IND,
  RIL_PARAM_RPI_ID,
  RIL_PARAM_RPI_ALL
} RILREMOTEPARTYINFOVALUEPARAM;
````


## -enum-fields




### -field RIL_PARAM_RPI_EXECUTOR


### -field RIL_PARAM_RPI_ADDRESS


### -field RIL_PARAM_RPI_SUBADDRESS


### -field RIL_PARAM_RPI_DESCRIPTION


### -field RIL_PARAM_RPI_NUM_PRES_IND


### -field RIL_PARAM_RPI_NAME_PRES_IND


### -field RIL_PARAM_RPI_ID


### -field RIL_PARAM_RPI_ALL

