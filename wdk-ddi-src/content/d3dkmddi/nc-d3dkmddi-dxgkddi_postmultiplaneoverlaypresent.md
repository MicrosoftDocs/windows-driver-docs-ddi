---
UID: NC:d3dkmddi.DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT
title: DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT
author: windows-driver-content
description: Called after a new multi-plane overlay configuration has taken effect, allowing the driver to optimize hardware state. Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.
old-location: display\dxgkddi_postmultiplaneoverlaypresent.htm
old-project: display
ms.assetid: C420DDE8-73D4-4D43-861C-A7B31B4C7DEC
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT, DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT callback function [Display Devices], d3dkmddi/DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT, display.dxgkddi_postmultiplaneoverlaypresent
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
-	DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT callback


## -description


Called after a new multi-plane overlay configuration has taken effect, allowing the driver to optimize hardware state.  Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.


## -prototype


````
NTSTATUS  DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT(
  _In_ const HANDLE                                hAdapter,
  _In_ const PDXGKARG_POSTMULTIPLANEOVERLAYPRESENT pPostMultiPlaneOverlayPresent
);
````


## -parameters




### -param hAdapter [in]

Identifies the adapter containing the overlay hardware.


### -param pPostPresent








#### - pPostMultiPlaneOverlayPresent [in]

A pointer to a DXGKARG_POSTMULTIPLANEOVERLAYPRESENT structure that describes the new overlay configuration recently committed.


## -returns



DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT returns the following values:

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
If the routine has been successfully completed. The driver should always return a success code.  Failures will result in a bugcheck.

</td>
</tr>
</table>
 




## -remarks



This function is called from PASSIVE level.

This function is only called when driver sets PostPresentNeeded of DXGKCB_NOTIFY_MPO_VSYNC_FLAGS member of the DXGKARGCB_NOTIFY_INTERRUPT_DATA structure in the VSYNC callback.

The driver can use this function to lower voltage levels, clocks, FIFO depths, or any other optimization that can save power.

The driver should not spend significant amount of time in this call because the call blocks the main GPU scheduler thread and delay could lead to present glitches. Time intensive actions should be queued as separate work items by driver and handled in background. In this scenario, any conflicts between the queued item and hardware changes demanded by future pre/post calls should be managed by driver. 



