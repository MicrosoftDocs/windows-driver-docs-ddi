---
UID: NC:hdaudio.PGET_LINK_POSITION_REGISTER
title: PGET_LINK_POSITION_REGISTER
author: windows-driver-content
description: The GetLinkPositionRegister routine retrieves a pointer to a DMA engine's link position register.The function pointer type for a GetLinkPositionRegister routine is defined as follows.
old-location: audio\getlinkpositionregister.htm
old-project: audio
ms.assetid: 8b8c7f61-c22a-421f-999f-291999bb243f
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.getlinkpositionregister, GetLinkPositionRegister callback function [Audio Devices], GetLinkPositionRegister, PGET_LINK_POSITION_REGISTER, PGET_LINK_POSITION_REGISTER, hdaudio/GetLinkPositionRegister, aud-prop2_715e978e-6396-479a-a953-6d17016306c4.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	hdaudio.h
apiname:
-	GetLinkPositionRegister
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---

# PGET_LINK_POSITION_REGISTER callback


## -description


The <code>GetLinkPositionRegister</code> routine retrieves a pointer to a DMA engine's link position register.

The function pointer type for a <code>GetLinkPositionRegister</code> routine is defined as follows.


## -prototype


````
PGET_LINK_POSITION_REGISTER GetLinkPositionRegister;

NTSTATUS GetLinkPositionRegister(
  _In_  PVOID  context,
  _In_  HANDLE handle,
  _Out_ PULONG *position
)
{ ... }
````


## -parameters




### -param _context [in]

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a> or <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


### -param Handle


### -param *Position








#### - handle [in]

Handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>.


#### - position [out]

Retrieves a pointer to the link position register. This parameter points to a caller-allocated PULONG variable into which the routine writes a pointer to the register. The HD Audio bus driver maps the register to a system virtual address that is accessible to the function driver.


## -returns



<code>GetLinkPositionRegister</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows a possible return status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the <i>handle</i> parameter value is invalid.

</td>
</tr>
</table>
 




## -remarks



For more information, see <a href="https://msdn.microsoft.com/6764affc-a4f0-4568-aa27-7f12e86b818b">Wall Clock and Link Position Registers</a>.




## -see-also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PGET_LINK_POSITION_REGISTER callback function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

