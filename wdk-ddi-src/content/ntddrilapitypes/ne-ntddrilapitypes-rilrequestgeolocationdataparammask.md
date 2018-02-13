---
UID: NE:ntddrilapitypes.RILREQUESTGEOLOCATIONDATAPARAMMASK
title: RILREQUESTGEOLOCATIONDATAPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrequestgeolocationdataparammask.htm
old-project: netvista
ms.assetid: 86b89336-56f9-4665-a0d3-37dc6ec6c377
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_PARAM_REQUESTGEOLOCATIONDATA_ALL, RIL_PARAM_REQUESTGEOLOCATIONDATA_SIZE, ntddrilapitypes/RILREQUESTGEOLOCATIONDATAPARAMMASK, RILREQUESTGEOLOCATIONDATAPARAMMASK enumeration [Network Drivers Starting with Windows Vista], netvista.rilrequestgeolocationdataparammask, RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTACCCURACY, ntddrilapitypes/RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTACCCURACY, RIL_PARAM_REQUESTGEOLOCATIONDATA_ALL, ntddrilapitypes/RIL_PARAM_REQUESTGEOLOCATIONDATA_SIZE, ntddrilapitypes/RIL_PARAM_REQUESTGEOLOCATIONDATA_MASK, ntddrilapitypes/RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTINFORMATION, RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTINFORMATION, RIL_PARAM_REQUESTGEOLOCATIONDATA_EXECUTOR, ntddrilapitypes/RIL_PARAM_REQUESTGEOLOCATIONDATA_EXECUTOR, RIL_PARAM_REQUESTGEOLOCATIONDATA_MASK, RILREQUESTGEOLOCATIONDATAPARAMMASK
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
-	RILREQUESTGEOLOCATIONDATAPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILREQUESTGEOLOCATIONDATAPARAMMASK
---

# RILREQUESTGEOLOCATIONDATAPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILREQUESTGEOLOCATIONDATAPARAMMASK { 
  RIL_PARAM_REQUESTGEOLOCATIONDATA_SIZE,
  RIL_PARAM_REQUESTGEOLOCATIONDATA_EXECUTOR,
  RIL_PARAM_REQUESTGEOLOCATIONDATA_MASK,
  RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTACCCURACY,
  RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTINFORMATION,
  RIL_PARAM_REQUESTGEOLOCATIONDATA_ALL
} RILREQUESTGEOLOCATIONDATAPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_NONE


### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_SIZE


### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_EXECUTOR


### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_MASK


### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTACCCURACY


### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTINFORMATION


### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_ALL

