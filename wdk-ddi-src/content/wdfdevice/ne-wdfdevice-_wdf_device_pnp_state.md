---
UID: NE:wdfdevice._WDF_DEVICE_PNP_STATE
title: _WDF_DEVICE_PNP_STATE (wdfdevice.h)
description: The WDF_DEVICE_PNP_STATE enumeration identifies all of the states that the framework's Plug and Play state machine can enter.
old-location: wdf\wdf_device_pnp_state.htm
tech.root: wdf
ms.assetid: b907a1ca-d9ef-45e9-9e1b-26e58e3e1e07
ms.date: 02/26/2018
keywords: ["_WDF_DEVICE_PNP_STATE enumeration"]
ms.keywords: "*PWDF_DEVICE_PNP_STATE, DFDeviceObjectGeneralRef_e9aab8ea-3d0c-44f3-bad9-cd21c6f1bd28.xml, PWDF_DEVICE_PNP_STATE, PWDF_DEVICE_PNP_STATE enumeration pointer, WDF_DEVICE_PNP_STATE, WDF_DEVICE_PNP_STATE enumeration, WdfDevStatePnpCheckForDevicePresence, WdfDevStatePnpEjectFailed, WdfDevStatePnpEjectHardware, WdfDevStatePnpEjectedWaitingForRemove, WdfDevStatePnpEnableInterfaces, WdfDevStatePnpFailed, WdfDevStatePnpFailedInit, WdfDevStatePnpFailedIoStarting, WdfDevStatePnpFailedOwnHardware, WdfDevStatePnpFailedPowerDown, WdfDevStatePnpFailedPowerPolicyRemoved, WdfDevStatePnpFailedStarted, WdfDevStatePnpFailedSurpriseRemoved, WdfDevStatePnpFailedWaitForRemove, WdfDevStatePnpFdoRemoved, WdfDevStatePnpFinal, WdfDevStatePnpHardwareAvailable, WdfDevStatePnpHardwareAvailablePowerPolicyFailed, WdfDevStatePnpInit, WdfDevStatePnpInitQueryRemove, WdfDevStatePnpInitQueryRemoveCanceled, WdfDevStatePnpInitStarting, WdfDevStatePnpInitSurpriseRemoved, WdfDevStatePnpInvalid, WdfDevStatePnpNull, WdfDevStatePnpObjectCreated, WdfDevStatePnpPdoInitFailed, WdfDevStatePnpPdoRemoved, WdfDevStatePnpPdoRestart, WdfDevStatePnpQueriedRemoving, WdfDevStatePnpQueriedSurpriseRemove, WdfDevStatePnpQueryCanceled, WdfDevStatePnpQueryRemoveAskDriver, WdfDevStatePnpQueryRemoveEnsureDeviceAwake, WdfDevStatePnpQueryRemovePending, WdfDevStatePnpQueryRemoveStaticCheck, WdfDevStatePnpQueryStopAskDriver, WdfDevStatePnpQueryStopEnsureDeviceAwake, WdfDevStatePnpQueryStopPending, WdfDevStatePnpQueryStopStaticCheck, WdfDevStatePnpRemoved, WdfDevStatePnpRemovedChildrenRemoved, WdfDevStatePnpRemovedPdoSurpriseRemoved, WdfDevStatePnpRemovedPdoWait, WdfDevStatePnpRemovedWaitForChildren, WdfDevStatePnpRemovingDisableInterfaces, WdfDevStatePnpRestart, WdfDevStatePnpRestartHardwareAvailable, WdfDevStatePnpRestartReleaseHardware, WdfDevStatePnpRestarting, WdfDevStatePnpStarted, WdfDevStatePnpStartedCancelRemove, WdfDevStatePnpStartedCancelStop, WdfDevStatePnpStartedRemoving, WdfDevStatePnpStartedStopping, WdfDevStatePnpStartingFromStopped, WdfDevStatePnpStopped, WdfDevStatePnpStoppedWaitForStartCompletion, WdfDevStatePnpSurpriseRemove, WdfDevStatePnpSurpriseRemoveIoStarted, _WDF_DEVICE_PNP_STATE, kmdf.wdf_device_pnp_state, wdf.wdf_device_pnp_state, wdfdevice/PWDF_DEVICE_PNP_STATE, wdfdevice/WDF_DEVICE_PNP_STATE, wdfdevice/WdfDevStatePnpCheckForDevicePresence, wdfdevice/WdfDevStatePnpEjectFailed, wdfdevice/WdfDevStatePnpEjectHardware, wdfdevice/WdfDevStatePnpEjectedWaitingForRemove, wdfdevice/WdfDevStatePnpEnableInterfaces, wdfdevice/WdfDevStatePnpFailed, wdfdevice/WdfDevStatePnpFailedInit, wdfdevice/WdfDevStatePnpFailedIoStarting, wdfdevice/WdfDevStatePnpFailedOwnHardware, wdfdevice/WdfDevStatePnpFailedPowerDown, wdfdevice/WdfDevStatePnpFailedPowerPolicyRemoved, wdfdevice/WdfDevStatePnpFailedStarted, wdfdevice/WdfDevStatePnpFailedSurpriseRemoved, wdfdevice/WdfDevStatePnpFailedWaitForRemove, wdfdevice/WdfDevStatePnpFdoRemoved, wdfdevice/WdfDevStatePnpFinal, wdfdevice/WdfDevStatePnpHardwareAvailable, wdfdevice/WdfDevStatePnpHardwareAvailablePowerPolicyFailed, wdfdevice/WdfDevStatePnpInit, wdfdevice/WdfDevStatePnpInitQueryRemove, wdfdevice/WdfDevStatePnpInitQueryRemoveCanceled, wdfdevice/WdfDevStatePnpInitStarting, wdfdevice/WdfDevStatePnpInitSurpriseRemoved, wdfdevice/WdfDevStatePnpInvalid, wdfdevice/WdfDevStatePnpNull, wdfdevice/WdfDevStatePnpObjectCreated, wdfdevice/WdfDevStatePnpPdoInitFailed, wdfdevice/WdfDevStatePnpPdoRemoved, wdfdevice/WdfDevStatePnpPdoRestart, wdfdevice/WdfDevStatePnpQueriedRemoving, wdfdevice/WdfDevStatePnpQueriedSurpriseRemove, wdfdevice/WdfDevStatePnpQueryCanceled, wdfdevice/WdfDevStatePnpQueryRemoveAskDriver, wdfdevice/WdfDevStatePnpQueryRemoveEnsureDeviceAwake, wdfdevice/WdfDevStatePnpQueryRemovePending, wdfdevice/WdfDevStatePnpQueryRemoveStaticCheck, wdfdevice/WdfDevStatePnpQueryStopAskDriver, wdfdevice/WdfDevStatePnpQueryStopEnsureDeviceAwake, wdfdevice/WdfDevStatePnpQueryStopPending, wdfdevice/WdfDevStatePnpQueryStopStaticCheck, wdfdevice/WdfDevStatePnpRemoved, wdfdevice/WdfDevStatePnpRemovedChildrenRemoved, wdfdevice/WdfDevStatePnpRemovedPdoSurpriseRemoved, wdfdevice/WdfDevStatePnpRemovedPdoWait, wdfdevice/WdfDevStatePnpRemovedWaitForChildren, wdfdevice/WdfDevStatePnpRemovingDisableInterfaces, wdfdevice/WdfDevStatePnpRestart, wdfdevice/WdfDevStatePnpRestartHardwareAvailable, wdfdevice/WdfDevStatePnpRestartReleaseHardware, wdfdevice/WdfDevStatePnpRestarting, wdfdevice/WdfDevStatePnpStarted, wdfdevice/WdfDevStatePnpStartedCancelRemove, wdfdevice/WdfDevStatePnpStartedCancelStop, wdfdevice/WdfDevStatePnpStartedRemoving, wdfdevice/WdfDevStatePnpStartedStopping, wdfdevice/WdfDevStatePnpStartingFromStopped, wdfdevice/WdfDevStatePnpStopped, wdfdevice/WdfDevStatePnpStoppedWaitForStartCompletion, wdfdevice/WdfDevStatePnpSurpriseRemove, wdfdevice/WdfDevStatePnpSurpriseRemoveIoStarted"
f1_keywords:
 - "wdfdevice/WDF_DEVICE_PNP_STATE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfdevice.h
api_name:
- WDF_DEVICE_PNP_STATE
product:
- Windows
targetos: Windows
req.typenames: WDF_DEVICE_PNP_STATE, *PWDF_DEVICE_PNP_STATE
---

# _WDF_DEVICE_PNP_STATE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The WDF_DEVICE_PNP_STATE enumeration identifies all of the states that the framework's Plug and Play state machine can enter.


## -enum-fields




### -field WdfDevStatePnpInvalid


### -field WdfDevStatePnpObjectCreated


### -field WdfDevStatePnpCheckForDevicePresence


### -field WdfDevStatePnpEjectFailed


### -field WdfDevStatePnpEjectHardware


### -field WdfDevStatePnpEjectedWaitingForRemove


### -field WdfDevStatePnpInit


### -field WdfDevStatePnpInitStarting


### -field WdfDevStatePnpInitSurpriseRemoved


### -field WdfDevStatePnpHardwareAvailable


### -field WdfDevStatePnpEnableInterfaces


### -field WdfDevStatePnpHardwareAvailablePowerPolicyFailed


### -field WdfDevStatePnpQueryRemoveAskDriver


### -field WdfDevStatePnpQueryRemovePending


### -field WdfDevStatePnpQueryRemoveStaticCheck


### -field WdfDevStatePnpQueriedRemoving


### -field WdfDevStatePnpQueryStopAskDriver


### -field WdfDevStatePnpQueryStopPending


### -field WdfDevStatePnpQueryStopStaticCheck


### -field WdfDevStatePnpQueryCanceled


### -field WdfDevStatePnpRemoved


### -field WdfDevStatePnpPdoRemoved


### -field WdfDevStatePnpRemovedPdoWait


### -field WdfDevStatePnpRemovedPdoSurpriseRemoved


### -field WdfDevStatePnpRemovingDisableInterfaces


### -field WdfDevStatePnpRestarting


### -field WdfDevStatePnpStarted


### -field WdfDevStatePnpStartedCancelStop


### -field WdfDevStatePnpStartedCancelRemove


### -field WdfDevStatePnpStartedRemoving


### -field WdfDevStatePnpStartingFromStopped


### -field WdfDevStatePnpStopped


### -field WdfDevStatePnpStoppedWaitForStartCompletion


### -field WdfDevStatePnpStartedStopping


### -field WdfDevStatePnpSurpriseRemove


### -field WdfDevStatePnpInitQueryRemove


### -field WdfDevStatePnpInitQueryRemoveCanceled


### -field WdfDevStatePnpFdoRemoved


### -field WdfDevStatePnpRemovedWaitForChildren


### -field WdfDevStatePnpQueriedSurpriseRemove


### -field WdfDevStatePnpSurpriseRemoveIoStarted


### -field WdfDevStatePnpFailedPowerDown


### -field WdfDevStatePnpFailedIoStarting


### -field WdfDevStatePnpFailedOwnHardware


### -field WdfDevStatePnpFailed


### -field WdfDevStatePnpFailedSurpriseRemoved


### -field WdfDevStatePnpFailedStarted


### -field WdfDevStatePnpFailedWaitForRemove


### -field WdfDevStatePnpFailedInit


### -field WdfDevStatePnpPdoInitFailed


### -field WdfDevStatePnpRestart


### -field WdfDevStatePnpRestartReleaseHardware


### -field WdfDevStatePnpRestartHardwareAvailable


### -field WdfDevStatePnpPdoRestart


### -field WdfDevStatePnpFinal


### -field WdfDevStatePnpRemovedChildrenRemoved


### -field WdfDevStatePnpQueryRemoveEnsureDeviceAwake


### -field WdfDevStatePnpQueryStopEnsureDeviceAwake


### -field WdfDevStatePnpFailedPowerPolicyRemoved


### -field WdfDevStatePnpNull


## -remarks



The WDF_DEVICE_PNP_STATE enumeration is used as a member type for  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_pnp_notification_data">WDF_DEVICE_PNP_NOTIFICATION_DATA</a> structure and as the return type for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepnpstate">WdfDeviceGetDevicePnpState</a> method.



