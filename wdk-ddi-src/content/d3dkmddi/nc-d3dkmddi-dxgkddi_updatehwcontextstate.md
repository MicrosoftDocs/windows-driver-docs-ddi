---
UID: NC:d3dkmddi.DXGKDDI_UPDATEHWCONTEXTSTATE
title: DXGKDDI_UPDATEHWCONTEXTSTATE
author: windows-driver-content
description: Used to update the hardware context state.
old-location: display\dxgkddi_updatehwcontextstate.htm
old-project: display
ms.assetid: 1187A302-CD7D-418E-B48F-74D1FF29C991
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddi_updatehwcontextstate, DXGKDDI_UPDATEHWCONTEXTSTATE callback function [Display Devices], DXGKDDI_UPDATEHWCONTEXTSTATE, d3dkmddi/DXGKDDI_UPDATEHWCONTEXTSTATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
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
req.irql: requires_(PASSIVE_LEVEL)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKDDI_UPDATEHWCONTEXTSTATE
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_UPDATEHWCONTEXTSTATE callback


## -description


Used to update the hardware context state.


## -prototype


````
NTSTATUS APIENTRY DXGKDDI_UPDATEHWCONTEXTSTATE(
  _In_ const HANDLE                        hAdapter,
  _In_ const PDXGKARG_UPDATEHWCONTEXTSTATE pUpdateHwContextState
);
````


## -parameters




### -param hAdapter [in]

A handle to the generated adapter.


### -param pUpdateHwContextState [in]

A pointer used by the function to update the hardware context state.


## -returns



Returns STATUS_SUCCESS if completed successfully.



