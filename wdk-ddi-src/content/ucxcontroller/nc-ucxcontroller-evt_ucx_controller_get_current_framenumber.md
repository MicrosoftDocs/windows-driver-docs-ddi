---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER
title: EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER
description: The client driver's implementation that UCX calls to retrieve the current 32-bit frame number.
old-location: buses\evt_ucx_controller_get_current_framenumber.htm
tech.root: usbref
ms.assetid: 2755d0fd-9801-4d54-89cb-54f8b984288c
ms.date: 05/07/2018
ms.keywords: EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER, EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER callback, EvtUcxControllerGetCurrentFrameNumber, EvtUcxControllerGetCurrentFrameNumber callback function [Buses], PEVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER, PEVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER callback function pointer [Buses], buses.evt_ucx_controller_get_current_framenumber, ucxcontroller/EvtUcxControllerGetCurrentFrameNumber
ms.topic: callback
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ucxcontroller.h
api_name:
-	PEVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER callback function


## -description


The client driver's implementation that UCX calls to retrieve the current 32-bit frame number.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param FrameNumber [out]

A pointer to the current 32-bit frame number.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The UCX client driver registers its <i>EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER</i> implementation with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
Controller_EvtControllerGetCurrentFrameNumber(
    UCXCONTROLLER   UcxController,
    PULONG          FrameNumber
)

{
    UNREFERENCED_PARAMETER(UcxController);

    //
    // TODO: Return the current 32-bit frame number.  Do not access the
    // controller registers if the controller is not in D0.
    //

    *FrameNumber = 0xFFFFFFFF;

    DbgTrace(TL_INFO, Controller, "Controller_EvtControllerGetCurrentFrameNumber");

    return STATUS_SUCCESS;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>
 

 

