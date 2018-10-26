---
UID: NS:wdfdevice._WDF_DEVICE_PNP_NOTIFICATION_DATA
title: "_WDF_DEVICE_PNP_NOTIFICATION_DATA"
author: windows-driver-content
description: The WDF_DEVICE_PNP_NOTIFICATION_DATA structure describes a state change within a device's Plug and Play state machine.
old-location: wdf\wdf_device_pnp_notification_data.htm
tech.root: wdf
ms.assetid: b49431bf-4b44-4d7b-b3a6-c3d7416bcb53
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_92c66935-afca-4567-bc55-cb3e3822201e.xml, WDF_DEVICE_PNP_NOTIFICATION_DATA, WDF_DEVICE_PNP_NOTIFICATION_DATA structure, _WDF_DEVICE_PNP_NOTIFICATION_DATA, kmdf.wdf_device_pnp_notification_data, wdf.wdf_device_pnp_notification_data, wdfdevice/WDF_DEVICE_PNP_NOTIFICATION_DATA
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_DEVICE_PNP_NOTIFICATION_DATA
product:
- Windows
targetos: Windows
req.typenames: WDF_DEVICE_PNP_NOTIFICATION_DATA
---

# _WDF_DEVICE_PNP_NOTIFICATION_DATA structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The WDF_DEVICE_PNP_NOTIFICATION_DATA structure describes a state change within a device's Plug and Play state machine.


## -struct-fields




### -field Type

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552513">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerator that identifies the type of state change that is being reported.


### -field Data


### -field Data.EnterState



##### EnterState.


### -field Data.EnterState.CurrentState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551262">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's current state.


### -field Data.EnterState.NewState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551262">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's next state.


### -field Data.PostProcessState



##### PostProcessState.


### -field Data.PostProcessState.CurrentState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551262">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's current state.


### -field Data.LeaveState



##### LeaveState.


### -field Data.LeaveState.CurrentState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551262">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's current state.


### -field Data.LeaveState.NewState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551262">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's next state.


## -remarks



The WDF_DEVICE_PNP_NOTIFICATION_DATA structure is an input argument to a driver's <a href="https://msdn.microsoft.com/5f08d331-0e58-45a3-93a3-b5e9a40b5af3">EvtDevicePnpStateChange</a> callback function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546057">WdfDeviceInitRegisterPnpStateChangeCallback</a>
 

 

