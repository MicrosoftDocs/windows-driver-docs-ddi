---
UID: NC:d3dumddi.PFND3DDDI_DECODEEXTENSIONEXECUTE
title: PFND3DDDI_DECODEEXTENSIONEXECUTE
author: windows-driver-content
description: The DecodeExtensionExecute function performs a decode operation by using the given Microsoft DirectX Video Accelerator (VA) nonstandard decode device.
old-location: display\decodeextensionexecute.htm
old-project: display
ms.assetid: 522a552a-4588-4dd1-b81f-73ccd4a1c0aa
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DecodeExtensionExecute, DecodeExtensionExecute callback function [Display Devices], PFND3DDDI_DECODEEXTENSIONEXECUTE, UserModeDisplayDriver_Functions_426d4fa5-389b-4aca-a1c9-233d3a54b949.xml, d3dumddi/DecodeExtensionExecute, display.decodeextensionexecute
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
-	DecodeExtensionExecute
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DECODEEXTENSIONEXECUTE callback


## -description


The <b>DecodeExtensionExecute</b> function performs a decode operation by using the given Microsoft DirectX Video Accelerator (VA) nonstandard decode device.


## -prototype


````
PFND3DDDI_DECODEEXTENSIONEXECUTE DecodeExtensionExecute;

__checkReturn HRESULT APIENTRY DecodeExtensionExecute(
  _In_          HANDLE                           hDevice,
  _Inout_ const D3DDDIARG_DECODEEXTENSIONEXECUTE *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodeextensionexecute.md">D3DDDIARG_DECODEEXTENSIONEXECUTE</a> structure that describes the DirectX VA decode operation to perform.


## -returns



<b>DecodeExtensionExecute</b> returns one of the following values:

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

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeextensionexecute.md">DecodeExtensionExecute</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



A user-mode display driver can implement the <b>DecodeExtensionExecute</b> function to support extensions to the standard decode types (that is, nonstandard decode GUIDs). These nonstandard decode types are useful for configuring encryption and other miscellaneous enhancements. 

<b>DecodeExtensionExecute</b> is called when DirectX VA 2.0 decoders require the nonstandard extensions.

For compatibility with DirectX VA 1.0 decoders that might require these nonstandard extensions, <b>DecodeExtensionExecute</b> is called whenever a DirectX VA 1.0 decoder makes an execution call in which any bDXVA_Func value that is greater than 4 is set in the most significant 8 bits of the <b>Function</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodeextensionexecute.md">D3DDDIARG_DECODEEXTENSIONEXECUTE</a> structure. <b>DecodeExtensionExecute</b> is also called whenever DirectX VA 1.0 decoder makes a configuration call in which any DXVA_ConfigQueryOrReplyFunc flag other than DXVA_QUERYORREPLYFUNCFLAG_DECODER_PROBE_QUERY (0xFFFFF1) or DXVA_QUERYORREPLYFUNCFLAG_DECODER_LOCK_QUERY (0xFFFFF5) flag is set in the most significant 24 bits of <b>Function</b>. For more information about the meanings for the bit settings of <b>Function</b>, see the <a href="https://msdn.microsoft.com/bfb1a98e-b9f0-4baa-b486-b2ff33a8bac5">DXVA_ConfigQueryOrReplyFlag and DXVA_ConfigQueryorReplyFunc Variables</a> and <a href="https://msdn.microsoft.com/6db9fa71-7bc2-4eb6-afcb-b16df48f7e8b">bDXVA_Func Variable</a> topics. 

Because of compatibility issues with DirectX VA 1.0 decoders that might make such a configuration call before DXVA_QUERYORREPLYFUNCFLAG_DECODER_LOCK_QUERY, those decoders can make such a configuration call also before a decode device is created. If such a configuration call is made before a decode device is created, the <b>hDecode</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodeextensionexecute.md">D3DDDIARG_DECODEEXTENSIONEXECUTE</a> structure that the <i>pData</i> parameter points to is set to <b>NULL</b>. In this situation, the driver might be required to return an error (for example, E_FAIL) if the driver cannot support the situation independent of a decode device. 




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodeextensionexecute.md">D3DDDIARG_DECODEEXTENSIONEXECUTE</a>



 

 


