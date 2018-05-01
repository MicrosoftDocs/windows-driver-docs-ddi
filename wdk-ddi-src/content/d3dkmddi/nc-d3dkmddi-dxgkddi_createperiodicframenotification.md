---
UID: NC:d3dkmddi.DXGKDDI_CREATEPERIODICFRAMENOTIFICATION
title: DXGKDDI_CREATEPERIODICFRAMENOTIFICATION
author: windows-driver-content
description: Used to create a periodic frame notification.
old-location: display\dxgkddi_createperiodicframenotification.htm
old-project: display
ms.assetid: EE11227A-E576-49C6-AEF1-CBE0AD788275
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_CREATEPERIODICFRAMENOTIFICATION, DXGKDDI_CREATEPERIODICFRAMENOTIFICATION callback, DXGKDDI_CREATEPERIODICFRAMENOTIFICATION callback function [Display Devices], d3dkmddi/DXGKDDI_CREATEPERIODICFRAMENOTIFICATION, display.dxgkddi_createperiodicframenotification
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
req.irql: requires_max_(PASSIVE_LEVEL)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DXGKDDI_CREATEPERIODICFRAMENOTIFICATION
product: Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_CREATEPERIODICFRAMENOTIFICATION callback function


## -description


Used to create a periodic frame notification.


## -parameters




### -param pCreatePeriodicFrameNotification [in]

A structure of type <i>PDXGKARG_CREATEPERIODICFRAMENOTIFICATION</i> containing the arguments needed to create a periodic frame notification.


## -returns



DXGKDDI_CREATEPERIODICFRAMENOTIFICATION returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
When a periodic frame notification has been successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
When a periodic frame notification does not have enough memory to be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that there was an invalid parameter passed to the call.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
When a periodic frame notification has not been successfully created.

</td>
</tr>
</table>
 



