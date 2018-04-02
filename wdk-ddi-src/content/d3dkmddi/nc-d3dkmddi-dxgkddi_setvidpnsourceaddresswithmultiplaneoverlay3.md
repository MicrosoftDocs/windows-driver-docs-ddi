---
UID: NC:d3dkmddi.DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
title: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
author: windows-driver-content
description: Called to change the overlay configuration being displayed.
old-location: display\dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.htm
old-project: display
ms.assetid: B4B6C5F0-AB67-4D30-B6A5-76B7596D22B6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 callback function [Display Devices], d3dkmddi/DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, display.dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 callback


## -description


Called to change the overlay configuration being displayed.


## -parameters




### -param hAdapter [in]

Identifies the adapter containing the overlay hardware.


### -param pSetVidPnSourceAddressWithMultiPlaneOverlay [in]

A pointer to a DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 structure that describes the surfaces and display options to present.


## -returns



DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 returns the following values:

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
If the routine has completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RETRY</b></dt>
</dl>
</td>
<td width="60%">
If the driver needs to be called at the PASSIVE_LEVEL. The driver should also set the DXGK_SETVIPNSOURCEADDRESS_OUTPUT_FLAGS.PrePresentNeeded flag.

</td>
</tr>
</table>
 




## -remarks



This function is typically called at interrupt level, but if the driver needs to perform hardware configuration that can only be performed at PASSIVE_LEVEL, the driver can request that this function be recalled at PASSIVE level by returning STATUS_RETRY and setting the DXGK_SETVIPNSOURCEADDRESS_OUTPUT_FLAGS.PrePresentNeeded flag.

Even when called at PASSIVE_LEVEL, the driver should avoid spending a significant amount of time in this call because the call blocks the main GPU scheduler thread and delay could lead to present glitches. Time intensive actions should be queued as separate work items by driver and handled in background. In this scenario, any conflicts between the queued item and hardware changes demanded by future pre/post calls should be managed by the driver. 



