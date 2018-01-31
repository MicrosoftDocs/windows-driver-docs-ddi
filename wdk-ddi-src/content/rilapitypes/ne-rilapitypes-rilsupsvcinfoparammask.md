---
UID: NE:rilapitypes.RILSUPSVCINFOPARAMMASK
title: RILSUPSVCINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupsvcinfoparammask_2.htm
old-project: netvista
ms.assetid: 52dd2092-939a-491b-af2d-2ea86eabf99a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSUPSVCINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_SSI_CALL_BARRING_PASSWORD, rilapitypes/RIL_PARAM_SSI_ALL, RIL_PARAM_SSI_SUPSVC_ACTION, RIL_PARAM_SSI_SUPSERVICE_DATA, RIL_PARAM_SSI_CONNECTED_ID_SETTINGS, rilapitypes/RIL_PARAM_SSI_ALPHA_IDENTIFIER, rilapitypes/RIL_PARAM_SSI_FROM_NETWORK, rilapitypes/RIL_PARAM_SSI_CALLER_ID_SETTINGS, RIL_PARAM_SSI_DIALED_ID_SETTINGS, rilapitypes/RIL_PARAM_SSI_FAILURE_REASON, RIL_PARAM_SSI_CALL_BARRING_TYPE, rilapitypes/RIL_PARAM_SSI_SUPSVC_TYPE, rilapitypes/RIL_PARAM_SSI_CALL_FORWARDING_REASON, RIL_PARAM_SSI_SUPSVC_TYPE, rilapitypes/RIL_PARAM_SSI_SUPSERVICE_DATA, RIL_PARAM_SSI_NEW_CALL_BARRING_PASSWORD, rilapitypes/RIL_PARAM_SSI_CALL_BARRING_TYPE, RIL_PARAM_SSI_CALL_FORWARDING_SETTINGS, netvista.rilsupsvcinfoparammask_2, rilapitypes/RIL_PARAM_SSI_CALL_BARRING_PASSWORD, RILSUPSVCINFOPARAMMASK, RIL_PARAM_SSI_FAILURE_REASON, RIL_PARAM_SSI_CALL_FORWARDING_REASON, rilapitypes/RIL_PARAM_SSI_HIDE_ID_SETTINGS, RIL_PARAM_SSI_FROM_NETWORK, rilapitypes/RIL_PARAM_SSI_DIALED_ID_SETTINGS, rilapitypes/RIL_PARAM_SSI_CONNECTED_ID_SETTINGS, rilapitypes/RIL_PARAM_SSI_CALL_FORWARDING_SETTINGS, RIL_PARAM_SSI_ALPHA_IDENTIFIER, rilapitypes/RIL_PARAM_SSI_NEW_CALL_BARRING_PASSWORD, RIL_PARAM_SSI_ALL, rilapitypes/RIL_PARAM_SSI_SUPSVC_ACTION, RIL_PARAM_SSI_INFOCLASSES, RIL_PARAM_SSI_CALLER_ID_SETTINGS, rilapitypes/RIL_PARAM_SSI_INFOCLASSES, RIL_PARAM_SSI_HIDE_ID_SETTINGS, rilapitypes/RILSUPSVCINFOPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILSUPSVCINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSUPSVCINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILSUPSVCINFOPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILSUPSVCINFOPARAMMASK { 
  RIL_PARAM_SSI_FROM_NETWORK,
  RIL_PARAM_SSI_FAILURE_REASON,
  RIL_PARAM_SSI_SUPSVC_ACTION,
  RIL_PARAM_SSI_SUPSVC_TYPE,
  RIL_PARAM_SSI_CALL_FORWARDING_REASON,
  RIL_PARAM_SSI_CALL_BARRING_TYPE,
  RIL_PARAM_SSI_INFOCLASSES,
  RIL_PARAM_SSI_ALPHA_IDENTIFIER,
  RIL_PARAM_SSI_CALL_BARRING_PASSWORD,
  RIL_PARAM_SSI_NEW_CALL_BARRING_PASSWORD,
  RIL_PARAM_SSI_CALL_FORWARDING_SETTINGS,
  RIL_PARAM_SSI_CALLER_ID_SETTINGS,
  RIL_PARAM_SSI_DIALED_ID_SETTINGS,
  RIL_PARAM_SSI_HIDE_ID_SETTINGS,
  RIL_PARAM_SSI_CONNECTED_ID_SETTINGS,
  RIL_PARAM_SSI_SUPSERVICE_DATA,
  RIL_PARAM_SSI_ALL
} RILSUPSVCINFOPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_SSI_EXECUTOR



#### - RIL_PARAM_SSI_FROM_NETWORK



#### - RIL_PARAM_SSI_FAILURE_REASON



#### - RIL_PARAM_SSI_SUPSVC_ACTION



#### - RIL_PARAM_SSI_SUPSVC_TYPE



#### - RIL_PARAM_SSI_CALL_FORWARDING_REASON



#### - RIL_PARAM_SSI_CALL_BARRING_TYPE



#### - RIL_PARAM_SSI_INFOCLASSES



#### - RIL_PARAM_SSI_ALPHA_IDENTIFIER



#### - RIL_PARAM_SSI_CALL_BARRING_PASSWORD



#### - RIL_PARAM_SSI_NEW_CALL_BARRING_PASSWORD



#### - RIL_PARAM_SSI_CALL_FORWARDING_SETTINGS



#### - RIL_PARAM_SSI_CALLER_ID_SETTINGS



#### - RIL_PARAM_SSI_DIALED_ID_SETTINGS



#### - RIL_PARAM_SSI_HIDE_ID_SETTINGS



#### - RIL_PARAM_SSI_CONNECTED_ID_SETTINGS



#### - RIL_PARAM_SSI_SUPSERVICE_DATA



#### - RIL_PARAM_SSI_ALL


