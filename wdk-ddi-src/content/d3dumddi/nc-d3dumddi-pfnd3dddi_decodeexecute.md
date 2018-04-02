---
UID: NC:d3dumddi.PFND3DDDI_DECODEEXECUTE
title: PFND3DDDI_DECODEEXECUTE
author: windows-driver-content
description: The DecodeExecute function performs a decode operation by using the given Microsoft DirectX Video Accelerator (VA) decode device.
old-location: display\decodeexecute.htm
old-project: display
ms.assetid: e12496c0-e3e4-437e-9f84-a30ee99b4541
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DecodeExecute, DecodeExecute callback function [Display Devices], PFND3DDDI_DECODEEXECUTE, UserModeDisplayDriver_Functions_6e4181b3-2ba5-4c77-a05a-4c8bb2d0d97c.xml, d3dumddi/DecodeExecute, display.decodeexecute
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	DecodeExecute
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DECODEEXECUTE callback


## -description


The <b>DecodeExecute</b> function performs a decode operation by using the given Microsoft DirectX Video Accelerator (VA) decode device.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543001">D3DDDIARG_DECODEEXECUTE</a> structure that describes the DirectX VA decode operation to perform.


## -returns



<b>DecodeExecute</b> returns one of the following values:

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
The DirectX VA decode operation is successfully performed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/e12496c0-e3e4-437e-9f84-a30ee99b4541">DecodeExecute</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



The Microsoft Direct3D runtime calls the <b>DecodeExecute</b> function for all of the standard DirectX VA decode operations. When <b>DecodeExecute</b> is first called for each frame, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543001">D3DDDIARG_DECODEEXECUTE</a> structure that is specified by <b>pData</b> should contain all of the buffer information that is required for decoding the frame. <b>DecodeExecute</b> can subsequently be called for the same frame; however, these calls require only incremental data. If the GUID for the particular DirectX VA decode type does not use a buffer that is specified in D3DDDIARG_DECODEEXECUTE, the handle and description for the buffer are set to <b>NULL</b>. For example, because the MPEG2 decode type requires picture parameters, a macroblock buffer, and a residual-difference buffer, all of these items must be present in the first call for each frame. Depending on the size of the data, however, the Direct3D runtime might call <b>DecodeExecute</b> again to supply only additional residual-difference data that is required to decode the entire frame. 

DirectX VA 1.0 supported an external synchronization mechanism through a call to the <a href="https://msdn.microsoft.com/af62d169-665a-43d2-ac0c-cc8ce6ce42d0">DdMoCompQueryStatus</a> function. In DirectX VA 2.0, the user-mode display driver should perform its own synchronization, similar to the way it synchronizes the 3-D pipe. For more information about this synchronization, see <a href="https://msdn.microsoft.com/4c88bf8f-0f10-4281-b856-a0e056d69d0e">Synchronizing Video Decode Operations</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543001">D3DDDIARG_DECODEEXECUTE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

