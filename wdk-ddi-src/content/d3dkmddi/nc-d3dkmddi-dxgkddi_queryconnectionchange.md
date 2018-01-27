---
UID: NC:d3dkmddi.DXGKDDI_QUERYCONNECTIONCHANGE
title: DXGKDDI_QUERYCONNECTIONCHANGE
author: windows-driver-content
description: The OS calls this in response to a status change reported through DxgkCbIndicateConnectorChange or when the OutputFlags.ConnectorStatusChanges field indicates that a call to SetTimingsFromVidPn has detected connector status changes.
old-location: display\dxgkddi_queryconnectionchange.htm
old-project: display
ms.assetid: 8C09B692-3439-4ACD-942D-F7A107E2B4DA
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddi_queryconnectionchange, DXGKDDI_QUERYCONNECTIONCHANGE callback function [Display Devices], DXGKDDI_QUERYCONNECTIONCHANGE, d3dkmddi/DXGKDDI_QUERYCONNECTIONCHANGE
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
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	d3dkmddi.h
apiname: 
-	DXGKDDI_QUERYCONNECTIONCHANGE
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_QUERYCONNECTIONCHANGE callback


## -description


The OS calls this in response to a status change reported through DxgkCbIndicateConnectorChange or when the OutputFlags.ConnectorStatusChanges field indicates that a call to SetTimingsFromVidPn has detected connector status changes.


## -prototype


````
NTSTATUS APIENTRY DXGKDDI_QUERYCONNECTIONCHANGE(
  _In_ const HANDLE                         hAdapter,
  _In_       PDXGKARG_QUERYCONNECTIONCHANGE pQueryConnectionChange
);
````


## -parameters




### -param hAdapter [in]

A handle that identifies the adapter.


### -param pQueryConnectionChange [in]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryconnectionchange.md">DXGKARG_QUERYCONNECTIONCHANGE</a> structure that provides the OS allocated buffer into which the oldest change should be copied by the driver. The oldest change is judged by lowest ConnectionChangeId.


## -returns


<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_SUCCESS</dt>
</dl>
</td>
<td width="60%">
Returned if the routine succeeds and returns the requested change.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_ALREADY_COMPLETE</dt>
</dl>
</td>
<td width="60%">
Returned if the routine succeeds, but the changes have already been reported to the OS.

</td>
</tr>
</table> 



## -remarks


This function is always called at PASSIVE level so the supporting code should be made pageable.


