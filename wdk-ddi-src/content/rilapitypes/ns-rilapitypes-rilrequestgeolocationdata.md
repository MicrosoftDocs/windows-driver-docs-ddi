---
UID: NS:rilapitypes.RILREQUESTGEOLOCATIONDATA
title: RILREQUESTGEOLOCATIONDATA
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrequestgeolocationdata_2.htm
old-project: netvista
ms.assetid: 2d447c49-08ac-43c2-9f70-557494e82cfc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILREQUESTGEOLOCATIONDATA, rilapitypes/RILREQUESTGEOLOCATIONDATA, RILREQUESTGEOLOCATIONDATA, RILREQUESTGEOLOCATIONDATA structure [Network Drivers Starting with Windows Vista], netvista.rilrequestgeolocationdata_2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.lib: 
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
-	RILREQUESTGEOLOCATIONDATA
product: Windows
targetos: Windows
req.typenames: RILREQUESTGEOLOCATIONDATA, *LPRILREQUESTGEOLOCATIONDATA
req.product: Windows 10 or later.
---

# RILREQUESTGEOLOCATIONDATA structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILREQUESTGEOLOCATIONDATA {
  DWORD                          cbSize;
  DWORD                          dwParams;
  DWORD                          dwExecutor;
  RILGEOLOCATIONTYPEMASK         dwLocationInformationMask;
  RILGEOLOCATIONREQUESTACCURACY  dwLocationRequestAccuracy;
  RILGEOLOCATIONREQUESTINFO      rrRequestInformation;
} RILREQUESTGEOLOCATIONDATA, RILREQUESTGEOLOCATIONDATA;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwLocationInformationMask


### -field dwLocationRequestAccuracy


### -field rrRequestInformation

