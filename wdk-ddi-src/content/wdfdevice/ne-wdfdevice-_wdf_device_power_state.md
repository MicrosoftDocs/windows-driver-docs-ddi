---
UID: NE:wdfdevice._WDF_DEVICE_POWER_STATE
title: _WDF_DEVICE_POWER_STATE (wdfdevice.h)
description: The WDF_DEVICE_POWER_STATE enumeration identifies all of the states that the framework's power state machine can enter.
old-location: wdf\wdf_device_power_state.htm
tech.root: wdf
ms.date: 11/03/2021
keywords: ["WDF_DEVICE_POWER_STATE enumeration"]
ms.keywords: "*PWDF_DEVICE_POWER_STATE, PWDF_DEVICE_POWER_STATE, PWDF_DEVICE_POWER_STATE enumeration pointer, WDF_DEVICE_POWER_STATE, WDF_DEVICE_POWER_STATE enumeration"
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
req.typenames: WDF_DEVICE_POWER_STATE, *PWDF_DEVICE_POWER_STATE
f1_keywords:
 - _WDF_DEVICE_POWER_STATE
 - wdfdevice/_WDF_DEVICE_POWER_STATE
 - PWDF_DEVICE_POWER_STATE
 - wdfdevice/PWDF_DEVICE_POWER_STATE
 - WDF_DEVICE_POWER_STATE
 - wdfdevice/WDF_DEVICE_POWER_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - _WDF_DEVICE_POWER_STATE
 - PWDF_DEVICE_POWER_STATE
 - WDF_DEVICE_POWER_STATE
---

# _WDF_DEVICE_POWER_STATE enumeration


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

>[!NOTE]
>This enumeration is for Microsoft internal use only.

The <b>WDF_DEVICE_POWER_STATE</b> enumeration identifies all of the states that the framework's power state machine can enter.

## -enum-fields

### -field WdfDevStatePowerInvalid:0x00

### -field WdfDevStatePowerObjectCreated:0x300

### -field WdfDevStatePowerCheckDeviceType:0x301

### -field WdfDevStatePowerCheckDeviceTypeNP:0x302 | WdfDevStateNP

### -field WdfDevStatePowerCheckParentState:0x303

### -field WdfDevStatePowerCheckParentStateNP:0x304 | WdfDevStateNP

### -field WdfDevStatePowerEnablingWakeAtBus:0x305

### -field WdfDevStatePowerEnablingWakeAtBusNP:0x306 | WdfDevStateNP

### -field WdfDevStatePowerD0:0x307

### -field WdfDevStatePowerD0NP:0x308 | WdfDevStateNP

### -field WdfDevStatePowerD0BusWakeOwner:0x309

### -field WdfDevStatePowerD0BusWakeOwnerNP:0x30A | WdfDevStateNP

### -field WdfDevStatePowerD0ArmedForWake:0x30B

### -field WdfDevStatePowerD0ArmedForWakeNP:0x30C | WdfDevStateNP

### -field WdfDevStatePowerD0DisarmingWakeAtBus:0x30D

### -field WdfDevStatePowerD0DisarmingWakeAtBusNP:0x30E | WdfDevStateNP

### -field WdfDevStatePowerD0Starting:0x30F

### -field WdfDevStatePowerD0StartingConnectInterrupt:0x310

### -field WdfDevStatePowerD0StartingDmaEnable:0x311

### -field WdfDevStatePowerD0StartingStartSelfManagedIo:0x312

### -field WdfDevStatePowerDecideD0State:0x313

### -field WdfDevStatePowerGotoD3Stopped:0x314

### -field WdfDevStatePowerStopped:0x315

### -field WdfDevStatePowerStartingCheckDeviceType:0x316

### -field WdfDevStatePowerStartingChild:0x317

### -field WdfDevStatePowerDxDisablingWakeAtBus:0x318

### -field WdfDevStatePowerDxDisablingWakeAtBusNP:0x319 | WdfDevStateNP

### -field WdfDevStatePowerGotoDx:0x31A

### -field WdfDevStatePowerGotoDxNP:0x31B | WdfDevStateNP

### -field WdfDevStatePowerGotoDxIoStopped:0x31C

### -field WdfDevStatePowerGotoDxIoStoppedNP:0x31D | WdfDevStateNP

### -field WdfDevStatePowerGotoDxNPFailed:0x31E | WdfDevStateNP

### -field WdfDevStatePowerDx:0x31F

### -field WdfDevStatePowerDxNP:0x320 | WdfDevStateNP

### -field WdfDevStatePowerGotoDxArmedForWake:0x321

### -field WdfDevStatePowerGotoDxArmedForWakeNP:0x322 | WdfDevStateNP

### -field WdfDevStatePowerGotoDxIoStoppedArmedForWake:0x323

### -field WdfDevStatePowerGotoDxIoStoppedArmedForWakeNP:0x324 | WdfDevStateNP

### -field WdfDevStatePowerDxArmedForWake:0x325

### -field WdfDevStatePowerDxArmedForWakeNP:0x326 | WdfDevStateNP

### -field WdfDevStatePowerCheckParentStateArmedForWake:0x327

### -field WdfDevStatePowerCheckParentStateArmedForWakeNP:0x328 | WdfDevStateNP

### -field WdfDevStatePowerWaitForParentArmedForWake:0x329

### -field WdfDevStatePowerWaitForParentArmedForWakeNP:0x32A | WdfDevStateNP

### -field WdfDevStatePowerStartSelfManagedIo:0x32B

### -field WdfDevStatePowerStartSelfManagedIoNP:0x32C | WdfDevStateNP

### -field WdfDevStatePowerStartSelfManagedIoFailed:0x32D

### -field WdfDevStatePowerStartSelfManagedIoFailedNP:0x32E | WdfDevStateNP

### -field WdfDevStatePowerWaitForParent:0x32F

### -field WdfDevStatePowerWaitForParentNP:0x330 | WdfDevStateNP

### -field WdfDevStatePowerWakePending:0x331

### -field WdfDevStatePowerWakePendingNP:0x332 | WdfDevStateNP

### -field WdfDevStatePowerWaking:0x333

### -field WdfDevStatePowerWakingNP:0x334 | WdfDevStateNP

### -field WdfDevStatePowerWakingConnectInterrupt:0x335

### -field WdfDevStatePowerWakingConnectInterruptNP:0x336 | WdfDevStateNP

### -field WdfDevStatePowerWakingConnectInterruptFailed:0x337

### -field WdfDevStatePowerWakingConnectInterruptFailedNP:0x338 | WdfDevStateNP

### -field WdfDevStatePowerWakingDmaEnable:0x339

### -field WdfDevStatePowerWakingDmaEnableNP:0x33A | WdfDevStateNP

### -field WdfDevStatePowerWakingDmaEnableFailed:0x33B

### -field WdfDevStatePowerWakingDmaEnableFailedNP:0x33C | WdfDevStateNP

### -field WdfDevStatePowerReportPowerUpFailedDerefParent:0x33D

### -field WdfDevStatePowerReportPowerUpFailed:0x33E

### -field WdfDevStatePowerPowerFailedPowerDown:0x33F

### -field WdfDevStatePowerReportPowerDownFailed:0x340

### -field WdfDevStatePowerInitialConnectInterruptFailed:0x341

### -field WdfDevStatePowerInitialDmaEnableFailed:0x342

### -field WdfDevStatePowerInitialSelfManagedIoFailed:0x343

### -field WdfDevStatePowerInitialPowerUpFailedDerefParent:0x344

### -field WdfDevStatePowerInitialPowerUpFailed:0x345

### -field WdfDevStatePowerDxStoppedDisarmWake:0x346

### -field WdfDevStatePowerDxStoppedDisarmWakeNP:0x347 | WdfDevStateNP

### -field WdfDevStatePowerGotoDxStoppedDisableInterruptNP:0x348 | WdfDevStateNP

### -field WdfDevStatePowerGotoDxStopped:0x349

### -field WdfDevStatePowerDxStopped:0x34A

### -field WdfDevStatePowerGotoStopped:0x34B

### -field WdfDevStatePowerStoppedCompleteDx:0x34C

### -field WdfDevStatePowerDxStoppedDecideDxState:0x34D

### -field WdfDevStatePowerDxStoppedArmForWake:0x34E

### -field WdfDevStatePowerDxStoppedArmForWakeNP:0x34F | WdfDevStateNP

### -field WdfDevStatePowerFinalPowerDownFailed:0x350

### -field WdfDevStatePowerFinal:0x351

### -field WdfDevStatePowerGotoImplicitD3DisarmWakeAtBus:0x352

### -field WdfDevStatePowerUpFailed:0x353

### -field WdfDevStatePowerUpFailedDerefParent:0x354

### -field WdfDevStatePowerGotoDxFailed:0x355

### -field WdfDevStatePowerGotoDxStoppedDisableInterrupt:0x356

### -field WdfDevStatePowerUpFailedNP:0x357 | WdfDevStateNP

### -field WdfDevStatePowerUpFailedDerefParentNP:0x358 | WdfDevStateNP

### -field WdfDevStatePowerNotifyingD0ExitToWakeInterrupts:0x359

### -field WdfDevStatePowerNotifyingD0EntryToWakeInterrupts:0x35A

### -field WdfDevStatePowerNotifyingD0ExitToWakeInterruptsNP:0x35B | WdfDevStateNP

### -field WdfDevStatePowerNotifyingD0EntryToWakeInterruptsNP:0x35C | WdfDevStateNP

### -field WdfDevStatePowerInitialPowerUpFailedPowerDown:0x35D

### -field WdfDevStatePowerUpFailedPowerDown:0x35E

### -field WdfDevStatePowerUpFailedPowerDownNP:0x35F | WdfDevStateNP

### -field WdfDevStatePowerInitialSelfManagedIoFailedStarted:0x360

### -field WdfDevStatePowerStartSelfManagedIoFailedStarted:0x361

### -field WdfDevStatePowerStartSelfManagedIoFailedStartedNP:0x362 | WdfDevStateNP

### -field WdfDevStatePowerWakingPostHardwareEnabled:0x363

### -field WdfDevStatePowerWakingPostHardwareEnabledNP:0x364 | WdfDevStateNP

### -field WdfDevStatePowerWakingPostHardwareEnabledFailed:0x365

### -field WdfDevStatePowerWakingPostHardwareEnabledFailedNP:0x366 | WdfDevStateNP

### -field WdfDevStatePowerD0StartingPostHardwareEnabled:0x367

### -field WdfDevStatePowerInitialPostHardwareEnabledFailed:0x368

### -field WdfDevStatePowerNull:0x369



## -remarks

The <b>WDF_DEVICE_POWER_STATE</b> enumeration is used as a member type in the <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_notification_data">WDF_DEVICE_POWER_NOTIFICATION_DATA</a> structure and as the return type for the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepowerstate">WdfDeviceGetDevicePowerState</a> method.

