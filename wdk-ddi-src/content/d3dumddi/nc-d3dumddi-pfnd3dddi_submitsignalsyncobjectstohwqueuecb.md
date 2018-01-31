---
UID: NC:d3dumddi.PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
title: PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
author: windows-driver-content
description: A callback to submit a signal command to the hardware queue.
old-location: display\pfnd3dddi_submitsignalsyncobjectstohwqueuecb.htm
old-project: display
ms.assetid: D952A432-7B2C-43AC-9BC4-4335D2F37301
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3dddi_submitsignalsyncobjectstohwqueuecb, PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB callback function [Display Devices], PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB, d3dumddi/PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
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
-	d3dumddi.h
apiname:
-	PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB callback


## -description


A callback to submit a signal command to the hardware queue.


## -prototype


````
_Check_return_ HRESULT APIENTRY CALLBACK PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB(
  _In_ HANDLE                                           hDevice,
  _In_ D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE *const submitSignalSyncoObjectsToHwQueue
);
````


## -parameters




#### - hDevice [in]

A handle to the device.


### -param *






#### - submitSignalSyncoObjectsToHwQueue [in]

A pointer to the structure holding information on submitting a signal command to the hardware queue.


## -returns


<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The call was successfully completed.

</td>
</tr>
</table> 

This function might also return other HRESULT values.


