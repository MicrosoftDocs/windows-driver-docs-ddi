---
UID: NE:wdfdevice._WDF_DEVICE_POWER_STATE
title: _WDF_DEVICE_POWER_STATE (wdfdevice.h)
description: The WDF_DEVICE_POWER_STATE enumeration identifies all of the states that the framework's power state machine can enter.
old-location: wdf\wdf_device_power_state.htm
tech.root: wdf
ms.assetid: 06bb6465-afc6-4b92-b3d7-1c66f6c6c33d
ms.date: 02/26/2018
ms.keywords: "*PWDF_DEVICE_POWER_STATE, DFDeviceObjectGeneralRef_f8548618-261b-4461-adfa-eeee324e67c2.xml, PWDF_DEVICE_POWER_STATE, PWDF_DEVICE_POWER_STATE enumeration pointer, WDF_DEVICE_POWER_STATE, WDF_DEVICE_POWER_STATE enumeration, WdfDevStatePowerCheckDeviceType, WdfDevStatePowerCheckDeviceTypeNP, WdfDevStatePowerCheckParentState, WdfDevStatePowerCheckParentStateArmedForWake, WdfDevStatePowerCheckParentStateArmedForWakeNP, WdfDevStatePowerCheckParentStateNP, WdfDevStatePowerD0, WdfDevStatePowerD0ArmedForWake, WdfDevStatePowerD0ArmedForWakeNP, WdfDevStatePowerD0BusWakeOwner, WdfDevStatePowerD0BusWakeOwnerNP, WdfDevStatePowerD0DisarmingWakeAtBus, WdfDevStatePowerD0DisarmingWakeAtBusNP, WdfDevStatePowerD0NP, WdfDevStatePowerD0Starting, WdfDevStatePowerD0StartingConnectInterrupt, WdfDevStatePowerD0StartingDmaEnable, WdfDevStatePowerD0StartingStartSelfManagedIo, WdfDevStatePowerDecideD0State, WdfDevStatePowerDx, WdfDevStatePowerDxArmedForWake, WdfDevStatePowerDxArmedForWakeNP, WdfDevStatePowerDxDisablingWakeAtBus, WdfDevStatePowerDxDisablingWakeAtBusNP, WdfDevStatePowerDxNP, WdfDevStatePowerDxStopped, WdfDevStatePowerDxStoppedArmForWake, WdfDevStatePowerDxStoppedArmForWakeNP, WdfDevStatePowerDxStoppedDecideDxState, WdfDevStatePowerDxStoppedDisarmWake, WdfDevStatePowerDxStoppedDisarmWakeNP, WdfDevStatePowerEnablingWakeAtBus, WdfDevStatePowerEnablingWakeAtBusNP, WdfDevStatePowerFinal, WdfDevStatePowerFinalPowerDownFailed, WdfDevStatePowerGotoD3Stopped, WdfDevStatePowerGotoDx, WdfDevStatePowerGotoDxArmedForWake, WdfDevStatePowerGotoDxArmedForWakeNP, WdfDevStatePowerGotoDxFailed, WdfDevStatePowerGotoDxIoStopped, WdfDevStatePowerGotoDxIoStoppedArmedForWake, WdfDevStatePowerGotoDxIoStoppedArmedForWakeNP, WdfDevStatePowerGotoDxIoStoppedNP, WdfDevStatePowerGotoDxNP, WdfDevStatePowerGotoDxNPFailed, WdfDevStatePowerGotoDxStopped, WdfDevStatePowerGotoDxStoppedDisableInterrupt, WdfDevStatePowerGotoDxStoppedDisableInterruptNP, WdfDevStatePowerGotoImplicitD3DisarmWakeAtBus, WdfDevStatePowerGotoStopped, WdfDevStatePowerInitialConnectInterruptFailed, WdfDevStatePowerInitialDmaEnableFailed, WdfDevStatePowerInitialPowerUpFailed, WdfDevStatePowerInitialPowerUpFailedDerefParent, WdfDevStatePowerInitialPowerUpFailedPowerDown, WdfDevStatePowerInitialSelfManagedIoFailed, WdfDevStatePowerInitialSelfManagedIoFailedStarted, WdfDevStatePowerInvalid, WdfDevStatePowerNotifyingD0EntryToWakeInterrupts, WdfDevStatePowerNotifyingD0EntryToWakeInterruptsNP, WdfDevStatePowerNotifyingD0ExitToWakeInterrupts, WdfDevStatePowerNotifyingD0ExitToWakeInterruptsNP, WdfDevStatePowerNull, WdfDevStatePowerObjectCreated, WdfDevStatePowerPowerFailedPowerDown, WdfDevStatePowerReportPowerDownFailed, WdfDevStatePowerReportPowerUpFailed, WdfDevStatePowerReportPowerUpFailedDerefParent, WdfDevStatePowerStartSelfManagedIo, WdfDevStatePowerStartSelfManagedIoFailed, WdfDevStatePowerStartSelfManagedIoFailedNP, WdfDevStatePowerStartSelfManagedIoFailedStarted, WdfDevStatePowerStartSelfManagedIoFailedStartedNP, WdfDevStatePowerStartSelfManagedIoNP, WdfDevStatePowerStartingCheckDeviceType, WdfDevStatePowerStartingChild, WdfDevStatePowerStopped, WdfDevStatePowerStoppedCompleteDx, WdfDevStatePowerUpFailed, WdfDevStatePowerUpFailedDerefParent, WdfDevStatePowerUpFailedDerefParentNP, WdfDevStatePowerUpFailedNP, WdfDevStatePowerUpFailedPowerDown, WdfDevStatePowerUpFailedPowerDownNP, WdfDevStatePowerWaitForParent, WdfDevStatePowerWaitForParentArmedForWake, WdfDevStatePowerWaitForParentArmedForWakeNP, WdfDevStatePowerWaitForParentNP, WdfDevStatePowerWakePending, WdfDevStatePowerWakePendingNP, WdfDevStatePowerWaking, WdfDevStatePowerWakingConnectInterrupt, WdfDevStatePowerWakingConnectInterruptFailed, WdfDevStatePowerWakingConnectInterruptFailedNP, WdfDevStatePowerWakingConnectInterruptNP, WdfDevStatePowerWakingDmaEnable, WdfDevStatePowerWakingDmaEnableFailed, WdfDevStatePowerWakingDmaEnableFailedNP, WdfDevStatePowerWakingDmaEnableNP, WdfDevStatePowerWakingNP, _WDF_DEVICE_POWER_STATE, kmdf.wdf_device_power_state, wdf.wdf_device_power_state, wdfdevice/PWDF_DEVICE_POWER_STATE, wdfdevice/WDF_DEVICE_POWER_STATE, wdfdevice/WdfDevStatePowerCheckDeviceType, wdfdevice/WdfDevStatePowerCheckDeviceTypeNP, wdfdevice/WdfDevStatePowerCheckParentState, wdfdevice/WdfDevStatePowerCheckParentStateArmedForWake, wdfdevice/WdfDevStatePowerCheckParentStateArmedForWakeNP, wdfdevice/WdfDevStatePowerCheckParentStateNP, wdfdevice/WdfDevStatePowerD0, wdfdevice/WdfDevStatePowerD0ArmedForWake, wdfdevice/WdfDevStatePowerD0ArmedForWakeNP, wdfdevice/WdfDevStatePowerD0BusWakeOwner, wdfdevice/WdfDevStatePowerD0BusWakeOwnerNP, wdfdevice/WdfDevStatePowerD0DisarmingWakeAtBus, wdfdevice/WdfDevStatePowerD0DisarmingWakeAtBusNP, wdfdevice/WdfDevStatePowerD0NP, wdfdevice/WdfDevStatePowerD0Starting, wdfdevice/WdfDevStatePowerD0StartingConnectInterrupt, wdfdevice/WdfDevStatePowerD0StartingDmaEnable, wdfdevice/WdfDevStatePowerD0StartingStartSelfManagedIo, wdfdevice/WdfDevStatePowerDecideD0State, wdfdevice/WdfDevStatePowerDx, wdfdevice/WdfDevStatePowerDxArmedForWake, wdfdevice/WdfDevStatePowerDxArmedForWakeNP, wdfdevice/WdfDevStatePowerDxDisablingWakeAtBus, wdfdevice/WdfDevStatePowerDxDisablingWakeAtBusNP, wdfdevice/WdfDevStatePowerDxNP, wdfdevice/WdfDevStatePowerDxStopped, wdfdevice/WdfDevStatePowerDxStoppedArmForWake, wdfdevice/WdfDevStatePowerDxStoppedArmForWakeNP, wdfdevice/WdfDevStatePowerDxStoppedDecideDxState, wdfdevice/WdfDevStatePowerDxStoppedDisarmWake, wdfdevice/WdfDevStatePowerDxStoppedDisarmWakeNP, wdfdevice/WdfDevStatePowerEnablingWakeAtBus, wdfdevice/WdfDevStatePowerEnablingWakeAtBusNP, wdfdevice/WdfDevStatePowerFinal, wdfdevice/WdfDevStatePowerFinalPowerDownFailed, wdfdevice/WdfDevStatePowerGotoD3Stopped, wdfdevice/WdfDevStatePowerGotoDx, wdfdevice/WdfDevStatePowerGotoDxArmedForWake, wdfdevice/WdfDevStatePowerGotoDxArmedForWakeNP, wdfdevice/WdfDevStatePowerGotoDxFailed, wdfdevice/WdfDevStatePowerGotoDxIoStopped, wdfdevice/WdfDevStatePowerGotoDxIoStoppedArmedForWake, wdfdevice/WdfDevStatePowerGotoDxIoStoppedArmedForWakeNP, wdfdevice/WdfDevStatePowerGotoDxIoStoppedNP, wdfdevice/WdfDevStatePowerGotoDxNP, wdfdevice/WdfDevStatePowerGotoDxNPFailed, wdfdevice/WdfDevStatePowerGotoDxStopped, wdfdevice/WdfDevStatePowerGotoDxStoppedDisableInterrupt, wdfdevice/WdfDevStatePowerGotoDxStoppedDisableInterruptNP, wdfdevice/WdfDevStatePowerGotoImplicitD3DisarmWakeAtBus, wdfdevice/WdfDevStatePowerGotoStopped, wdfdevice/WdfDevStatePowerInitialConnectInterruptFailed, wdfdevice/WdfDevStatePowerInitialDmaEnableFailed, wdfdevice/WdfDevStatePowerInitialPowerUpFailed, wdfdevice/WdfDevStatePowerInitialPowerUpFailedDerefParent, wdfdevice/WdfDevStatePowerInitialPowerUpFailedPowerDown, wdfdevice/WdfDevStatePowerInitialSelfManagedIoFailed, wdfdevice/WdfDevStatePowerInitialSelfManagedIoFailedStarted, wdfdevice/WdfDevStatePowerInvalid, wdfdevice/WdfDevStatePowerNotifyingD0EntryToWakeInterrupts, wdfdevice/WdfDevStatePowerNotifyingD0EntryToWakeInterruptsNP, wdfdevice/WdfDevStatePowerNotifyingD0ExitToWakeInterrupts, wdfdevice/WdfDevStatePowerNotifyingD0ExitToWakeInterruptsNP, wdfdevice/WdfDevStatePowerNull, wdfdevice/WdfDevStatePowerObjectCreated, wdfdevice/WdfDevStatePowerPowerFailedPowerDown, wdfdevice/WdfDevStatePowerReportPowerDownFailed, wdfdevice/WdfDevStatePowerReportPowerUpFailed, wdfdevice/WdfDevStatePowerReportPowerUpFailedDerefParent, wdfdevice/WdfDevStatePowerStartSelfManagedIo, wdfdevice/WdfDevStatePowerStartSelfManagedIoFailed, wdfdevice/WdfDevStatePowerStartSelfManagedIoFailedNP, wdfdevice/WdfDevStatePowerStartSelfManagedIoFailedStarted, wdfdevice/WdfDevStatePowerStartSelfManagedIoFailedStartedNP, wdfdevice/WdfDevStatePowerStartSelfManagedIoNP, wdfdevice/WdfDevStatePowerStartingCheckDeviceType, wdfdevice/WdfDevStatePowerStartingChild, wdfdevice/WdfDevStatePowerStopped, wdfdevice/WdfDevStatePowerStoppedCompleteDx, wdfdevice/WdfDevStatePowerUpFailed, wdfdevice/WdfDevStatePowerUpFailedDerefParent, wdfdevice/WdfDevStatePowerUpFailedDerefParentNP, wdfdevice/WdfDevStatePowerUpFailedNP, wdfdevice/WdfDevStatePowerUpFailedPowerDown, wdfdevice/WdfDevStatePowerUpFailedPowerDownNP, wdfdevice/WdfDevStatePowerWaitForParent, wdfdevice/WdfDevStatePowerWaitForParentArmedForWake, wdfdevice/WdfDevStatePowerWaitForParentArmedForWakeNP, wdfdevice/WdfDevStatePowerWaitForParentNP, wdfdevice/WdfDevStatePowerWakePending, wdfdevice/WdfDevStatePowerWakePendingNP, wdfdevice/WdfDevStatePowerWaking, wdfdevice/WdfDevStatePowerWakingConnectInterrupt, wdfdevice/WdfDevStatePowerWakingConnectInterruptFailed, wdfdevice/WdfDevStatePowerWakingConnectInterruptFailedNP, wdfdevice/WdfDevStatePowerWakingConnectInterruptNP, wdfdevice/WdfDevStatePowerWakingDmaEnable, wdfdevice/WdfDevStatePowerWakingDmaEnableFailed, wdfdevice/WdfDevStatePowerWakingDmaEnableFailedNP, wdfdevice/WdfDevStatePowerWakingDmaEnableNP, wdfdevice/WdfDevStatePowerWakingNP"
ms.topic: enum
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
-	WDF_DEVICE_POWER_STATE
product:
- Windows
targetos: Windows
req.typenames: WDF_DEVICE_POWER_STATE, *PWDF_DEVICE_POWER_STATE
---

# _WDF_DEVICE_POWER_STATE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_DEVICE_POWER_STATE</b> enumeration identifies all of the states that the framework's power state machine can enter.


## -enum-fields




### -field WdfDevStatePowerInvalid


### -field WdfDevStatePowerObjectCreated


### -field WdfDevStatePowerCheckDeviceType


### -field WdfDevStatePowerCheckDeviceTypeNP


### -field WdfDevStatePowerCheckParentState


### -field WdfDevStatePowerCheckParentStateNP


### -field WdfDevStatePowerEnablingWakeAtBus


### -field WdfDevStatePowerEnablingWakeAtBusNP


### -field WdfDevStatePowerD0


### -field WdfDevStatePowerD0NP


### -field WdfDevStatePowerD0BusWakeOwner


### -field WdfDevStatePowerD0BusWakeOwnerNP


### -field WdfDevStatePowerD0ArmedForWake


### -field WdfDevStatePowerD0ArmedForWakeNP


### -field WdfDevStatePowerD0DisarmingWakeAtBus


### -field WdfDevStatePowerD0DisarmingWakeAtBusNP


### -field WdfDevStatePowerD0Starting


### -field WdfDevStatePowerD0StartingConnectInterrupt


### -field WdfDevStatePowerD0StartingDmaEnable


### -field WdfDevStatePowerD0StartingStartSelfManagedIo


### -field WdfDevStatePowerDecideD0State


### -field WdfDevStatePowerGotoD3Stopped


### -field WdfDevStatePowerStopped


### -field WdfDevStatePowerStartingCheckDeviceType


### -field WdfDevStatePowerStartingChild


### -field WdfDevStatePowerDxDisablingWakeAtBus


### -field WdfDevStatePowerDxDisablingWakeAtBusNP


### -field WdfDevStatePowerGotoDx


### -field WdfDevStatePowerGotoDxNP


### -field WdfDevStatePowerGotoDxIoStopped


### -field WdfDevStatePowerGotoDxIoStoppedNP


### -field WdfDevStatePowerGotoDxNPFailed


### -field WdfDevStatePowerDx


### -field WdfDevStatePowerDxNP


### -field WdfDevStatePowerGotoDxArmedForWake


### -field WdfDevStatePowerGotoDxArmedForWakeNP


### -field WdfDevStatePowerGotoDxIoStoppedArmedForWake


### -field WdfDevStatePowerGotoDxIoStoppedArmedForWakeNP


### -field WdfDevStatePowerDxArmedForWake


### -field WdfDevStatePowerDxArmedForWakeNP


### -field WdfDevStatePowerCheckParentStateArmedForWake


### -field WdfDevStatePowerCheckParentStateArmedForWakeNP


### -field WdfDevStatePowerWaitForParentArmedForWake


### -field WdfDevStatePowerWaitForParentArmedForWakeNP


### -field WdfDevStatePowerStartSelfManagedIo


### -field WdfDevStatePowerStartSelfManagedIoNP


### -field WdfDevStatePowerStartSelfManagedIoFailed


### -field WdfDevStatePowerStartSelfManagedIoFailedNP


### -field WdfDevStatePowerWaitForParent


### -field WdfDevStatePowerWaitForParentNP


### -field WdfDevStatePowerWakePending


### -field WdfDevStatePowerWakePendingNP


### -field WdfDevStatePowerWaking


### -field WdfDevStatePowerWakingNP


### -field WdfDevStatePowerWakingConnectInterrupt


### -field WdfDevStatePowerWakingConnectInterruptNP


### -field WdfDevStatePowerWakingConnectInterruptFailed


### -field WdfDevStatePowerWakingConnectInterruptFailedNP


### -field WdfDevStatePowerWakingDmaEnable


### -field WdfDevStatePowerWakingDmaEnableNP


### -field WdfDevStatePowerWakingDmaEnableFailed


### -field WdfDevStatePowerWakingDmaEnableFailedNP


### -field WdfDevStatePowerReportPowerUpFailedDerefParent


### -field WdfDevStatePowerReportPowerUpFailed


### -field WdfDevStatePowerPowerFailedPowerDown


### -field WdfDevStatePowerReportPowerDownFailed


### -field WdfDevStatePowerInitialConnectInterruptFailed


### -field WdfDevStatePowerInitialDmaEnableFailed


### -field WdfDevStatePowerInitialSelfManagedIoFailed


### -field WdfDevStatePowerInitialPowerUpFailedDerefParent


### -field WdfDevStatePowerInitialPowerUpFailed


### -field WdfDevStatePowerDxStoppedDisarmWake


### -field WdfDevStatePowerDxStoppedDisarmWakeNP


### -field WdfDevStatePowerGotoDxStoppedDisableInterruptNP


### -field WdfDevStatePowerGotoDxStopped


### -field WdfDevStatePowerDxStopped


### -field WdfDevStatePowerGotoStopped


### -field WdfDevStatePowerStoppedCompleteDx


### -field WdfDevStatePowerDxStoppedDecideDxState


### -field WdfDevStatePowerDxStoppedArmForWake


### -field WdfDevStatePowerDxStoppedArmForWakeNP


### -field WdfDevStatePowerFinalPowerDownFailed


### -field WdfDevStatePowerFinal


### -field WdfDevStatePowerGotoImplicitD3DisarmWakeAtBus


### -field WdfDevStatePowerUpFailed


### -field WdfDevStatePowerUpFailedDerefParent


### -field WdfDevStatePowerGotoDxFailed


### -field WdfDevStatePowerGotoDxStoppedDisableInterrupt


### -field WdfDevStatePowerUpFailedNP


### -field WdfDevStatePowerUpFailedDerefParentNP


### -field WdfDevStatePowerNotifyingD0ExitToWakeInterrupts


### -field WdfDevStatePowerNotifyingD0EntryToWakeInterrupts


### -field WdfDevStatePowerNotifyingD0ExitToWakeInterruptsNP


### -field WdfDevStatePowerNotifyingD0EntryToWakeInterruptsNP


### -field WdfDevStatePowerInitialPowerUpFailedPowerDown


### -field WdfDevStatePowerUpFailedPowerDown


### -field WdfDevStatePowerUpFailedPowerDownNP


### -field WdfDevStatePowerInitialSelfManagedIoFailedStarted


### -field WdfDevStatePowerStartSelfManagedIoFailedStarted


### -field WdfDevStatePowerStartSelfManagedIoFailedStartedNP


### -field WdfDevStatePowerNull


## -remarks



The <b>WDF_DEVICE_POWER_STATE</b> enumeration is used as a member type in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551268">WDF_DEVICE_POWER_NOTIFICATION_DATA</a> structure and as the return type for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545985">WdfDeviceGetDevicePowerState</a> method.



