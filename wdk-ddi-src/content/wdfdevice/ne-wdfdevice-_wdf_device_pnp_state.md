---
UID: NE:wdfdevice._WDF_DEVICE_PNP_STATE
title: _WDF_DEVICE_PNP_STATE (wdfdevice.h)
description: The WDF_DEVICE_PNP_STATE enumeration identifies all of the states that the framework's Plug and Play state machine can enter.
old-location: wdf\wdf_device_pnp_state.htm
tech.root: wdf
ms.date: 11/01/2021
keywords: ["WDF_DEVICE_PNP_STATE enumeration"]
ms.keywords: "*PWDF_DEVICE_PNP_STATE, PWDF_DEVICE_PNP_STATE, PWDF_DEVICE_PNP_STATE enumeration pointer, WDF_DEVICE_PNP_STATE, WDF_DEVICE_PNP_STATE enumeration"
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
targetos: Windows
req.typenames: WDF_DEVICE_PNP_STATE, *PWDF_DEVICE_PNP_STATE
f1_keywords:
 - _WDF_DEVICE_PNP_STATE
 - wdfdevice/_WDF_DEVICE_PNP_STATE
 - PWDF_DEVICE_PNP_STATE
 - wdfdevice/PWDF_DEVICE_PNP_STATE
 - WDF_DEVICE_PNP_STATE
 - wdfdevice/WDF_DEVICE_PNP_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - _WDF_DEVICE_PNP_STATE
 - PWDF_DEVICE_PNP_STATE
 - WDF_DEVICE_PNP_STATE
---

# _WDF_DEVICE_PNP_STATE enumeration


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

>[!NOTE]
>This enumeration is for Microsoft internal use only.

The WDF_DEVICE_PNP_STATE enumeration identifies all of the states that the framework's Plug and Play state machine can enter.

## -enum-fields

### -field WdfDevStatePnpInvalid=0x00

### -field WdfDevStatePnpObjectCreated=0x1,=0x100,

### -field WdfDevStatePnpCheckForDevicePresence=0x1,=0x101,

### -field WdfDevStatePnpEjectFailed=0x1,=0x102,

### -field WdfDevStatePnpEjectHardware=0x1,=0x103,

### -field WdfDevStatePnpEjectedWaitingForRemove=0x1,=0x104,

### -field WdfDevStatePnpInit=0x1,=0x105,

### -field WdfDevStatePnpInitStarting=0x1,=0x106,

### -field WdfDevStatePnpInitSurpriseRemoved=0x1,=0x107,

### -field WdfDevStatePnpHardwareAvailable=0x1,=0x108,

### -field WdfDevStatePnpEnableInterfaces=0x109,

### -field WdfDevStatePnpHardwareAvailablePowerPolicyFailed=0x10A,

### -field WdfDevStatePnpQueryRemoveAskDriver=0x10B,

### -field WdfDevStatePnpQueryRemovePending=0x10C,

### -field WdfDevStatePnpQueryRemoveStaticCheck=0x10D,

### -field WdfDevStatePnpQueriedRemoving=0x10E,

### -field WdfDevStatePnpQueryStopAskDriver=0x10F,

### -field WdfDevStatePnpQueryStopPending=0x110,

### -field WdfDevStatePnpQueryStopStaticCheck=0x111,

### -field WdfDevStatePnpQueryCanceled=0x112,

### -field WdfDevStatePnpRemoved=0x113,

### -field WdfDevStatePnpPdoRemoved=0x114,

### -field WdfDevStatePnpRemovedPdoWait=0x115,

### -field WdfDevStatePnpRemovedPdoSurpriseRemoved=0x116,

### -field WdfDevStatePnpRemovingDisableInterfaces=0x117,

### -field WdfDevStatePnpRestarting=0x118,

### -field WdfDevStatePnpStarted=0x119,

### -field WdfDevStatePnpStartedCancelStop=0x11A,

### -field WdfDevStatePnpStartedCancelRemove=0x11B,

### -field WdfDevStatePnpStartedRemoving=0x11C,

### -field WdfDevStatePnpStartingFromStopped=0x11D,

### -field WdfDevStatePnpStopped=0x11E,

### -field WdfDevStatePnpStoppedWaitForStartCompletion=0x11F,

### -field WdfDevStatePnpStartedStopping=0x120,

### -field WdfDevStatePnpSurpriseRemove=0x121,

### -field WdfDevStatePnpInitQueryRemove=0x122,

### -field WdfDevStatePnpInitQueryRemoveCanceled=0x123,

### -field WdfDevStatePnpFdoRemoved=0x124,

### -field WdfDevStatePnpRemovedWaitForChildren=0x125,

### -field WdfDevStatePnpQueriedSurpriseRemove=0x126,

### -field WdfDevStatePnpSurpriseRemoveIoStarted=0x127,

### -field WdfDevStatePnpFailedPowerDown=0x128,

### -field WdfDevStatePnpFailedIoStarting=0x129,

### -field WdfDevStatePnpFailedOwnHardware=0x12A,

### -field WdfDevStatePnpFailed=0x12B,

### -field WdfDevStatePnpFailedSurpriseRemoved=0x12C,

### -field WdfDevStatePnpFailedStarted=0x12D,

### -field WdfDevStatePnpFailedWaitForRemove=0x12E,

### -field WdfDevStatePnpFailedInit=0x12F,

### -field WdfDevStatePnpPdoInitFailed=0x130,

### -field WdfDevStatePnpRestart=0x131,

### -field WdfDevStatePnpRestartReleaseHardware=0x132,

### -field WdfDevStatePnpRestartHardwareAvailable=0x133,

### -field WdfDevStatePnpPdoRestart=0x134,

### -field WdfDevStatePnpFinal=0x135,

### -field WdfDevStatePnpRemovedChildrenRemoved=0x136,

### -field WdfDevStatePnpQueryRemoveEnsureDeviceAwake=0x137,

### -field WdfDevStatePnpQueryStopEnsureDeviceAwake=0x138,

### -field WdfDevStatePnpFailedPowerPolicyRemoved=0x139,

### -field WdfDevStatePnpNull=0x13A,

## -remarks

The WDF_DEVICE_PNP_STATE enumeration is used as a member type for  the <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_pnp_notification_data">WDF_DEVICE_PNP_NOTIFICATION_DATA</a> structure and as the return type for the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepnpstate">WdfDeviceGetDevicePnpState</a> method.

