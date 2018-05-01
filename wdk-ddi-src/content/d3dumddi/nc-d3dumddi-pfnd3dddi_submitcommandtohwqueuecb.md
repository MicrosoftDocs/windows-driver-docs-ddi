---
UID: NC:d3dumddi.PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB
title: PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB
author: windows-driver-content
description: A callback to submit a command to the hardware queue.
old-location: display\pfnd3dddi_submitcommandtohwqueuecb.htm
old-project: display
ms.assetid: 8E8B0FE6-ACE5-4610-A0F7-95D426A4AA97
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB, PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB callback, PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB callback function [Display Devices], d3dumddi/PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB, display.pfnd3dddi_submitcommandtohwqueuecb
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SUBMITCOMMANDTOHWQUEUECB callback function


## -description


A callback to submit a command to the hardware queue.


## -parameters




### -param hDevice [in]

A handle to the device.


### -param *








#### - submitCommandToHwQueue [in]

A pointer to the structure holding information on submitting a command to the hardware queue.


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



