---
UID: NS:d3dkmthk._D3DKMT_GETDEVICESTATE
title: _D3DKMT_GETDEVICESTATE (d3dkmthk.h)
description: The D3DKMT_GETDEVICESTATE structure describes parameters for retrieving the state of a device.
old-location: display\d3dkmt_getdevicestate.htm
ms.assetid: b90f8b63-51d3-4de4-9d8b-91926150fd30
ms.date: 05/10/2018
keywords: ["D3DKMT_GETDEVICESTATE structure"]
ms.keywords: D3DKMT_GETDEVICESTATE, D3DKMT_GETDEVICESTATE structure [Display Devices], OpenGL_Structs_39a99244-3951-4a2f-a92d-4aec50589cde.xml, _D3DKMT_GETDEVICESTATE, d3dkmthk/D3DKMT_GETDEVICESTATE, display.d3dkmt_getdevicestate
f1_keywords:
 - "d3dkmthk/D3DKMT_GETDEVICESTATE"
 - "D3DKMT_GETDEVICESTATE"
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
- D3DKMT_GETDEVICESTATE
targetos: Windows
tech.root: display
req.typenames: D3DKMT_GETDEVICESTATE
---

# _D3DKMT_GETDEVICESTATE structure


## -description


The D3DKMT_GETDEVICESTATE structure describes parameters for retrieving the state of a device. 


## -struct-fields




### -field hDevice

[in] A handle to the device that status is requested for.


### -field StateType

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ne-d3dkmthk-_d3dkmt_devicestate_type">D3DKMT_DEVICESTATE_TYPE</a>-typed value that indicates the type of status to retrieve for the device.


### -field ExecutionState

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ne-d3dkmthk-_d3dkmt_deviceexecution_state">D3DKMT_DEVICEEXECUTION_STATE</a>-typed value that indicates the execution status of the device. The union that is contained in D3DKMT_GETDEVICESTATE holds a value from this enumeration if the <b>StateType</b> member is D3DKMT_DEVICESTATE_EXECUTION. 


### -field PresentState

[in/out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_devicepresent_state">D3DKMT_DEVICEPRESENT_STATE</a> structure that describes parameters for retrieving the present status of the device. The union that is contained in D3DKMT_GETDEVICESTATE holds a structure of this type if the <b>StateType</b> member is D3DKMT_DEVICESTATE_PRESENT. 


### -field ResetState

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_devicereset_state">D3DKMT_DEVICERESET_STATE</a> structure that describes the reset status of the device. The union that is contained in D3DKMT_GETDEVICESTATE holds a structure of this type if the <b>StateType</b> member is D3DKMT_DEVICESTATE_RESET. 


### -field PresentStateDWM

 


### -field PageFaultState

 


### -field PresentQueueState

 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtgetdevicestate">D3DKMTGetDeviceState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ne-d3dkmthk-_d3dkmt_deviceexecution_state">D3DKMT_DEVICEEXECUTION_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_devicepresent_state">D3DKMT_DEVICEPRESENT_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_devicereset_state">D3DKMT_DEVICERESET_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ne-d3dkmthk-_d3dkmt_devicestate_type">D3DKMT_DEVICESTATE_TYPE</a>
 

 

