---
UID: NC:d3dkmddi.DXGKDDI_CREATEPERIODICFRAMENOTIFICATION
title: DXGKDDI_CREATEPERIODICFRAMENOTIFICATION
author: windows-driver-content
description: Used to create a periodic frame notification.
old-location: display\dxgkddi_createperiodicframenotification.htm
old-project: display
ms.assetid: EE11227A-E576-49C6-AEF1-CBE0AD788275
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
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
req.alt-api: DXGKDDI_CREATEPERIODICFRAMENOTIFICATION
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: requires_max_(PASSIVE_LEVEL)
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_CREATEPERIODICFRAMENOTIFICATION callback



## -description
Used to create a periodic frame notification.



## -prototype

````
NTSTATUS APIENTRY DXGKDDI_CREATEPERIODICFRAMENOTIFICATION(
  _In_ const PDXGKARG_CREATEPERIODICFRAMENOTIFICATION pCreatePeriodicFrameNotification
);
````


## -parameters

### -param pCreatePeriodicFrameNotification [in]

A structure of type <i>PDXGKARG_CREATEPERIODICFRAMENOTIFICATION</i> containing the arguments needed to create a periodic frame notification.


## -returns
DXGKDDI_CREATEPERIODICFRAMENOTIFICATION returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>When a periodic frame notification has been successfully created.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>When a periodic frame notification does not have enough memory to be allocated.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Indicates that there was an invalid parameter passed to the call.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>When a periodic frame notification has not been successfully created.

 


## -remarks
