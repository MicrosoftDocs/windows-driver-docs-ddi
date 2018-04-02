---
UID: NC:d3dumddi.PFND3DDDI_EXTENSIONEXECUTE
title: PFND3DDDI_EXTENSIONEXECUTE
author: windows-driver-content
description: The ExtensionExecute function performs an operation by using the given Microsoft DirectX Video Accelerator (VA) extension device.
old-location: display\extensionexecute.htm
old-project: display
ms.assetid: a3f73651-bfff-48fa-aa61-477b8af7fa07
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ExtensionExecute, ExtensionExecute callback function [Display Devices], PFND3DDDI_EXTENSIONEXECUTE, UserModeDisplayDriver_Functions_2972e743-bdb5-41ab-92ff-986b8335883b.xml, d3dumddi/ExtensionExecute, display.extensionexecute
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
-	ExtensionExecute
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_EXTENSIONEXECUTE callback


## -description


The <i>ExtensionExecute</i> function performs an operation by using the given Microsoft DirectX Video Accelerator (VA) extension device.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543112">D3DDDIARG_EXTENSIONEXECUTE</a> structure that describes the DirectX VA operation to perform.


## -returns



<i>ExtensionExecute</i> returns one of the following values:

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
The DirectX VA operation is successfully performed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>ExtensionExecute</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543112">D3DDDIARG_EXTENSIONEXECUTE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

