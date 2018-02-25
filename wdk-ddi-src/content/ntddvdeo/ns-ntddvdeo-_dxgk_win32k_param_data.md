---
UID: NS:ntddvdeo._DXGK_WIN32K_PARAM_DATA
title: "_DXGK_WIN32K_PARAM_DATA"
author: windows-driver-content
description: The DXGK_WIN32K_PARAM_DATA structure is reserved for system use.
old-location: display\dxgk_win32k_param_data.htm
old-project: display
ms.assetid: a6bb2127-64f7-402d-906e-199d5ec1b313
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PDXGK_WIN32K_PARAM_DATA, ,, 2, 3, A, D, DXGK_WIN32K_PARAM_DATA, DXGK_WIN32K_PARAM_DATA structure [Display Devices], G, I, K, M, N, P, PDXGK_WIN32K_PARAM_DATA, PDXGK_WIN32K_PARAM_DATA structure pointer [Display Devices], R, T, Video_Structs_40ff171a-ad28-44ae-bcad-bf93aba4ad6e.xml, W, X, _, _DXGK_WIN32K_PARAM_DATA, display.dxgk_win32k_param_data, ntddvdeo/DXGK_WIN32K_PARAM_DATA, ntddvdeo/PDXGK_WIN32K_PARAM_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
-	ntddvdeo.h
apiname:
-	DXGK_WIN32K_PARAM_DATA
product: Windows
targetos: Windows
req.typenames: DXGK_WIN32K_PARAM_DATA, *PDXGK_WIN32K_PARAM_DATA
---

# _DXGK_WIN32K_PARAM_DATA structure


## -description


The DXGK_WIN32K_PARAM_DATA structure is reserved for system use.


## -syntax


````
typedef struct _DXGK_WIN32K_PARAM_DATA {
  PVOID PathsArray;
  PVOID ModesArray;
  ULONG NumPathArrayElements;
  ULONG NumModeArrayElements;
  ULONG SDCFlags;
} DXGK_WIN32K_PARAM_DATA, *PDXGK_WIN32K_PARAM_DATA;
````


## -struct-fields




### -field PathsArray

Reserved for system use.


### -field ModesArray

Reserved for system use.


### -field NumPathArrayElements

Reserved for system use.


### -field NumModeArrayElements

Reserved for system use.


### -field SDCFlags

Reserved for system use.

