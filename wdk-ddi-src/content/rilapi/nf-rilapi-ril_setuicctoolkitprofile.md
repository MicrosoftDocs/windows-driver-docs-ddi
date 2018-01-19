---
UID: NF:rilapi.RIL_SetUiccToolkitProfile
title: RIL_SetUiccToolkitProfile function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setuicctoolkitprofile.htm
old-project: netvista
ms.assetid: 123bf713-d238-491a-bc53-1f35dbb34feb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RIL_SetUiccToolkitProfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rilapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RIL_SetUiccToolkitProfile
req.alt-loc: rilapi.h
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
req.typenames: *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_SetUiccToolkitProfile function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            



## -syntax

````
HRESULT  RIL_SetUiccToolkitProfile(
   HRIL                         hRil,
   LPVOID                       lpContext,
   const RILUICCTOOLKITPROFILE  lpToolkitProfile
);
````


## -parameters

### -param hRil 


### -param lpContext 


### -param lpToolkitProfile 


## -returns
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
