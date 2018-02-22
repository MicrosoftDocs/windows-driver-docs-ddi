---
UID: NS:rilapitypes.RILSUPSERVICEDATA
title: RILSUPSERVICEDATA
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupservicedata_2.htm
old-project: netvista
ms.assetid: e9faa47e-56f7-464b-ad6a-fbb543ca9d1d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILSUPSERVICEDATA, netvista.rilsupservicedata_2, RILSUPSERVICEDATA structure [Network Drivers Starting with Windows Vista], rilapitypes/RILSUPSERVICEDATA, RILSUPSERVICEDATA"
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
-	RILSUPSERVICEDATA
product: Windows
targetos: Windows
req.typenames: RILSUPSERVICEDATA, *LPRILSUPSERVICEDATA
req.product: Windows 10 or later.
---

# RILSUPSERVICEDATA structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSUPSERVICEDATA {
  DWORD                    cbSize;
  DWORD                    dwParams;
  DWORD                    dwExecutor;
  RILSUPSERVICEDATASTATUS  dwStatus;
  DWORD                    dwNetworkSSErrorCause;
  DWORD                    dwNetworkCCErrorCause;
  DWORD                    dwVendorErrorCause;
  DWORD                    dwDataSize;
  WCHAR [1]                wszData;
} RILSUPSERVICEDATA, RILSUPSERVICEDATA;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwStatus


### -field dwNetworkSSErrorCause


### -field dwNetworkCCErrorCause


### -field dwVendorErrorCause


### -field dwDataSize


### -field wszData

