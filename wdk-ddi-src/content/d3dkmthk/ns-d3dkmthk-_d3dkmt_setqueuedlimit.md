---
UID: NS:d3dkmthk._D3DKMT_SETQUEUEDLIMIT
title: _D3DKMT_SETQUEUEDLIMIT (d3dkmthk.h)
description: The D3DKMT_SETQUEUEDLIMIT structure describes parameters for setting or retrieving the limit for the number of operations of the given type that can be queued for the given device.
old-location: display\d3dkmt_setqueuedlimit.htm
ms.assetid: 4fe525b1-9c06-4e2c-9e57-041164905efe
ms.date: 05/10/2018
ms.keywords: D3DKMT_SETQUEUEDLIMIT, D3DKMT_SETQUEUEDLIMIT structure [Display Devices], OpenGL_Structs_3c7f7e33-f71a-4547-89ee-7dba69917a4f.xml, _D3DKMT_SETQUEUEDLIMIT, d3dkmthk/D3DKMT_SETQUEUEDLIMIT, display.d3dkmt_setqueuedlimit
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_SETQUEUEDLIMIT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SETQUEUEDLIMIT
---

# _D3DKMT_SETQUEUEDLIMIT structure


## -description


The D3DKMT_SETQUEUEDLIMIT structure describes parameters for setting or retrieving the limit for the number of operations of the given type that can be queued for the given device. 


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device to set or retrieve the limit of queued operations for.


### -field Type

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff548225">D3DKMT_QUEUEDLIMIT_TYPE</a>-typed value that indicates the type of operations to set or retrieve the queued limit for. 


### -field QueuedPresentLimit

[in/out] The limit for the number of present operations that can be queued for the device that is specified by <b>hDevice</b>. If the OpenGL installable client driver (ICD) sets <b>QueuedPresentLimit</b> to 0, the limit for the device is reset to the graphics adapter's default value, which is currently 3. The union that is contained in D3DKMT_SETQUEUEDLIMIT contains the limiting number if the <b>Type</b> member is D3DKMT_SET_QUEUEDLIMIT_PRESENT and retrieves the number if <b>Type</b> is D3DKMT_GET_QUEUEDLIMIT_PRESENT. 


### -field VidPnSourceId

[in] An integer that identifies a video present source that is in the path of a video present network (VidPN) topology. The union that is contained in D3DKMT_SETQUEUEDLIMIT contains the integer if the present operations are flips. 


### -field QueuedPendingFlipLimit

[in/out] The limit for the number of flip operations that can be queued for the device that is specified by <b>hDevice</b>. If the OpenGL ICD sets <b>QueuedPendingFlipLimit</b> to 0, the limit for the device is reset to the graphics adapter's default value, which is currently 1. The union that is contained in D3DKMT_SETQUEUEDLIMIT contains the limiting number if the present operations are flips. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547195">D3DKMTSetQueuedLimit</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548225">D3DKMT_QUEUEDLIMIT_TYPE</a>
 

 

