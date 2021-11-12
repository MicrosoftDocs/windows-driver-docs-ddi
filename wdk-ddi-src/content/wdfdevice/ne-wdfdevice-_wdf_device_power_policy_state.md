---
UID: NE:wdfdevice._WDF_DEVICE_POWER_POLICY_STATE
title: _WDF_DEVICE_POWER_POLICY_STATE (wdfdevice.h)
description: The WDF_DEVICE_POWER_POLICY_STATE enumeration identifies all of the states that the framework's power policy state machine can enter.
old-location: wdf\wdf_device_power_policy_state.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_DEVICE_POWER_POLICY_STATE enumeration"]
ms.keywords: "*PWDF_DEVICE_POWER_POLICY_STATE, PWDF_DEVICE_POWER_POLICY_STATE, PWDF_DEVICE_POWER_POLICY_STATE enumeration pointer, WDF_DEVICE_POWER_POLICY_STATE, WDF_DEVICE_POWER_POLICY_STATE enumeration"
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
req.typenames: WDF_DEVICE_POWER_POLICY_STATE, *PWDF_DEVICE_POWER_POLICY_STATE
f1_keywords:
 - _WDF_DEVICE_POWER_POLICY_STATE
 - wdfdevice/_WDF_DEVICE_POWER_POLICY_STATE
 - PWDF_DEVICE_POWER_POLICY_STATE
 - wdfdevice/PWDF_DEVICE_POWER_POLICY_STATE
 - WDF_DEVICE_POWER_POLICY_STATE
 - wdfdevice/WDF_DEVICE_POWER_POLICY_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - _WDF_DEVICE_POWER_POLICY_STATE
 - PWDF_DEVICE_POWER_POLICY_STATE
 - WDF_DEVICE_POWER_POLICY_STATE
---

# _WDF_DEVICE_POWER_POLICY_STATE enumeration


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

>[!NOTE]
>This enumeration is for Microsoft internal use only.

The WDF_DEVICE_POWER_POLICY_STATE enumeration identifies all of the states that the framework's power policy state machine can enter.

## -enum-fields

### -field WdfDevStatePwrPolInvalid:0x00

### -field WdfDevStatePwrPolObjectCreated:0x500

### -field WdfDevStatePwrPolStarting:0x501

### -field WdfDevStatePwrPolStartingSucceeded:0x502

### -field WdfDevStatePwrPolStartingFailed:0x503

### -field WdfDevStatePwrPolStartingDecideS0Wake:0x504

### -field WdfDevStatePwrPolStartedIdleCapable:0x505

### -field WdfDevStatePwrPolTimerExpiredNoWake:0x506

### -field WdfDevStatePwrPolTimerExpiredNoWakeCompletePowerDown:0x507

### -field WdfDevStatePwrPolWaitingUnarmed:0x508

### -field WdfDevStatePwrPolWaitingUnarmedQueryIdle:0x509

### -field WdfDevStatePwrPolS0NoWakePowerUp:0x50A

### -field WdfDevStatePwrPolS0NoWakeCompletePowerUp:0x50B

### -field WdfDevStatePwrPolSystemSleepFromDeviceWaitingUnarmed:0x50C

### -field WdfDevStatePwrPolSystemSleepNeedWake:0x50D

### -field WdfDevStatePwrPolSystemSleepNeedWakeCompletePowerUp:0x50E

### -field WdfDevStatePwrPolSystemSleepPowerRequestFailed:0x50F

### -field WdfDevStatePwrPolCheckPowerPageable:0x510

### -field WdfDevStatePwrPolSleepingWakeWakeArrived:0x511

### -field WdfDevStatePwrPolSleepingWakeRevertArmWake:0x512

### -field WdfDevStatePwrPolSystemAsleepWakeArmed:0x513

### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabled:0x514

### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceled:0x515

### -field WdfDevStatePwrPolSystemWakeDeviceWakeDisarm:0x516

### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggered:0x517

### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0:0x518

### -field WdfDevStatePwrPolSystemWakeDeviceWokeDisarm:0x519

### -field WdfDevStatePwrPolSleepingWakeWakeArrivedNP: 0x51A | WdfDevStateNP

### -field WdfDevStatePwrPolSleepingWakeRevertArmWakeNP: 0x51B | WdfDevStateNP

### -field WdfDevStatePwrPolSleepingWakePowerDownFailed:0x51C

### -field WdfDevStatePwrPolSleepingWakePowerDownFailedWakeCanceled:0x51D

### -field WdfDevStatePwrPolSystemAsleepWakeArmedNP: 0x51E | WdfDevStateNP

### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabledNP: 0x51F | WdfDevStateNP

### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceledNP: 0x520 | WdfDevStateNP

### -field WdfDevStatePwrPolSystemWakeDeviceWakeDisarmNP: 0x521 | WdfDevStateNP

### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredNP: 0x522 | WdfDevStateNP

### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0NP: 0x523 | WdfDevStateNP

### -field WdfDevStatePwrPolSystemWakeDeviceWokeDisarmNP: 0x524 | WdfDevStateNP

### -field WdfDevStatePwrPolSystemWakeDeviceWakeCompletePowerUp:0x525

### -field WdfDevStatePwrPolSleeping:0x526

### -field WdfDevStatePwrPolSleepingNoWakePowerDown:0x527

### -field WdfDevStatePwrPolSleepingNoWakeCompletePowerDown:0x528

### -field WdfDevStatePwrPolSleepingNoWakeDxRequestFailed:0x529

### -field WdfDevStatePwrPolSleepingWakePowerDown:0x52A

### -field WdfDevStatePwrPolSleepingSendWake:0x52B

### -field WdfDevStatePwrPolSystemAsleepNoWake:0x52C

### -field WdfDevStatePwrPolSystemWakeDeviceWakeDisabled:0x52D

### -field WdfDevStatePwrPolSystemWakeDeviceToD0:0x52E

### -field WdfDevStatePwrPolSystemWakeDeviceToD0CompletePowerUp:0x52F

### -field WdfDevStatePwrPolSystemWakeQueryIdle:0x530

### -field WdfDevStatePwrPolStartedWakeCapable:0x531

### -field WdfDevStatePwrPolTimerExpiredDecideUsbSS:0x532

### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDown:0x533

### -field WdfDevStatePwrPolTimerExpiredWakeCapableSendWake:0x534

### -field WdfDevStatePwrPolTimerExpiredWakeCapableUsbSS:0x535

### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeArrived:0x536

### -field WdfDevStatePwrPolTimerExpiredWakeCapableCancelWake:0x537

### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeCanceled:0x538

### -field WdfDevStatePwrPolTimerExpiredWakeCapableCleanup:0x539

### -field WdfDevStatePwrPolTimerExpiredWakeCapableDxAllocFailed:0x53A

### -field WdfDevStatePwrPolTimerExpiredWakeCompletedPowerDown:0x53B

### -field WdfDevStatePwrPolTimerExpiredWakeCompletedPowerUp:0x53C

### -field WdfDevStatePwrPolWaitingArmedUsbSS:0x53D

### -field WdfDevStatePwrPolWaitingArmed:0x53E

### -field WdfDevStatePwrPolWaitingArmedQueryIdle:0x53F

### -field WdfDevStatePwrPolIoPresentArmed:0x540

### -field WdfDevStatePwrPolIoPresentArmedWakeCanceled:0x541

### -field WdfDevStatePwrPolS0WakeDisarm:0x542

### -field WdfDevStatePwrPolS0WakeCompletePowerUp:0x543

### -field WdfDevStatePwrPolTimerExpiredWakeSucceeded:0x544

### -field WdfDevStatePwrPolTimerExpiredWakeCompletedDisarm:0x545

### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeSucceeded:0x546

### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeFailed:0x547

### -field WdfDevStatePwrPolWakeFailedUsbSS:0x548

### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedCancelWake:0x549

### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeCanceled:0x54A

### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedUsbSS:0x54B

### -field WdfDevStatePwrPolCancelingWakeForSystemSleep:0x54C

### -field WdfDevStatePwrPolCancelingWakeForSystemSleepWakeCanceled:0x54D

### -field WdfDevStatePwrPolDisarmingWakeForSystemSleepCompletePowerUp:0x54E

### -field WdfDevStatePwrPolPowerUpForSystemSleepFailed:0x54F

### -field WdfDevStatePwrPolWokeFromS0UsbSS:0x550

### -field WdfDevStatePwrPolWokeFromS0:0x551

### -field WdfDevStatePwrPolWokeFromS0NotifyDriver:0x552

### -field WdfDevStatePwrPolStoppingResetDevice:0x553

### -field WdfDevStatePwrPolStoppingResetDeviceCompletePowerUp:0x554

### -field WdfDevStatePwrPolStoppingResetDeviceFailed:0x555

### -field WdfDevStatePwrPolStoppingD0:0x556

### -field WdfDevStatePwrPolStoppingD0Failed:0x557

### -field WdfDevStatePwrPolStoppingDisarmWake:0x558

### -field WdfDevStatePwrPolStoppingDisarmWakeCancelWake:0x559

### -field WdfDevStatePwrPolStoppingDisarmWakeWakeCanceled:0x55A

### -field WdfDevStatePwrPolStopping:0x55B

### -field WdfDevStatePwrPolStoppingFailed:0x55C

### -field WdfDevStatePwrPolStoppingSendStatus:0x55D

### -field WdfDevStatePwrPolStoppingCancelTimer:0x55E

### -field WdfDevStatePwrPolStoppingWaitForIdleTimeout:0x55F

### -field WdfDevStatePwrPolStoppingCancelUsbSS:0x560

### -field WdfDevStatePwrPolStoppingWaitForUsbSSCompletion:0x561

### -field WdfDevStatePwrPolStoppingCancelWake:0x562

### -field WdfDevStatePwrPolStopped:0x563

### -field WdfDevStatePwrPolCancelUsbSS:0x564

### -field WdfDevStatePwrPolStarted:0x565

### -field WdfDevStatePwrPolStartedCancelTimer:0x566

### -field WdfDevStatePwrPolStartedWaitForIdleTimeout:0x567

### -field WdfDevStatePwrPolStartedWakeCapableCancelTimerForSleep:0x568

### -field WdfDevStatePwrPolStartedWakeCapableWaitForIdleTimeout:0x569

### -field WdfDevStatePwrPolStartedWakeCapableSleepingUsbSS:0x56A

### -field WdfDevStatePwrPolStartedIdleCapableCancelTimerForSleep:0x56B

### -field WdfDevStatePwrPolStartedIdleCapableWaitForIdleTimeout:0x56C

### -field WdfDevStatePwrPolDeviceD0PowerRequestFailed:0x56D

### -field WdfDevStatePwrPolDevicePowerRequestFailed:0x56E

### -field WdfDevStatePwrPolGotoDx:0x56F

### -field WdfDevStatePwrPolGotoDxInDx:0x570

### -field WdfDevStatePwrPolDx:0x571

### -field WdfDevStatePwrPolGotoD0:0x572

### -field WdfDevStatePwrPolGotoD0InD0:0x573

### -field WdfDevStatePwrPolFinal:0x574

### -field WdfDevStatePwrPolSleepingPowerDownNotProcessed:0x575

### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownNotProcessed:0x576

### -field WdfDevStatePwrPolTimerExpiredNoWakePowerDownNotProcessed:0x577

### -field WdfDevStatePwrPolTimerExpiredNoWakePoweredDownDisableIdleTimer:0x578

### -field WdfDevStatePwrPolStoppingWaitingForImplicitPowerDown:0x579

### -field WdfDevStatePwrPolStoppingPoweringUp:0x57A

### -field WdfDevStatePwrPolStoppingPoweringDown:0x57B

### -field WdfDevStatePwrPolPowerUpForSystemSleepNotSeen:0x57C

### -field WdfDevStatePwrPolWaitingArmedStoppingCancelUsbSS:0x57D

### -field WdfDevStatePwrPolWaitingArmedWakeFailedCancelUsbSS:0x57E

### -field WdfDevStatePwrPolWaitingArmedIoPresentCancelUsbSS:0x57F

### -field WdfDevStatePwrPolWaitingArmedWakeSucceededCancelUsbSS:0x580

### -field WdfDevStatePwrPolCancelingUsbSSForSystemSleep:0x581

### -field WdfDevStatePwrPolStoppingD0CancelUsbSS:0x582

### -field WdfDevStatePwrPolStartingPoweredUp:0x583

### -field WdfDevStatePwrPolIdleCapableDeviceIdle:0x584

### -field WdfDevStatePwrPolDeviceIdleReturnToActive:0x585

### -field WdfDevStatePwrPolDeviceIdleSleeping:0x586

### -field WdfDevStatePwrPolDeviceIdleStopping:0x587

### -field WdfDevStatePwrPolTimerExpiredNoWakeUndoPowerDown:0x588

### -field WdfDevStatePwrPolWakeCapableDeviceIdle:0x589

### -field WdfDevStatePwrPolWakeCapableUsbSSCompleted:0x58A

### -field WdfDevStatePwrPolTimerExpiredWakeCapableUndoPowerDown:0x58B

### -field WdfDevStatePwrPolTimerExpiredWakeCompletedHardwareStarted:0x58C

### -field WdfDevStatePwrPolStoppedRemoving:0x58D

### -field WdfDevStatePwrPolRemoved:0x58E

### -field WdfDevStatePwrPolRestarting:0x58F

### -field WdfDevStatePwrPolRestartingFailed:0x590

### -field WdfDevStatePwrPolStartingPoweredUpFailed:0x591

### -field WdfDevStatePwrPolTimerExpiredNoWakeReturnToActive:0x592

### -field WdfDevStatePwrPolWaitingArmedWakeInterruptFired:0x593

### -field WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFired:0x594

### -field WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFiredNP: 0x595 | WdfDevStateNP

### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeInterruptArrived:0x596

### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeInterruptArrived:0x597

### -field WdfDevStatePwrPolWaitingArmedWakeInterruptFiredDuringPowerDown:0x598

### -field WdfDevStatePwrPolStartedNotIdleCapableDirectedDown:0x599

### -field WdfDevStatePwrPolStartedIdleCapableTimerCanceledForSleep:0x59A

### -field WdfDevStatePwrPolTimerExpiredNoWakeUndoPowerDownWaitForDirectedUp:0x59B

### -field WdfDevStatePwrPolIdleCapableTimerNotExpiredDirectedDown:0x59C

### -field WdfDevStatePwrPolIdleCapableDirectedDownTriggerDPNR:0x59D

### -field WdfDevStatePwrPolWaitingUnarmedDirectedDown:0x59E

### -field WdfDevStatePwrPolIdleCapableDirectedDownTriggerDPR:0x59F

### -field WdfDevStatePwrPolStartedWakeCapableTimerCanceledForSleep:0x5A0

### -field WdfDevStatePwrPolWakeCapableTimerNotExpiredDirectedDown:0x5A1

### -field WdfDevStatePwrPolWakeCapableDirectedDownTriggerDPNR:0x5A2

### -field WdfDevStatePwrPolTimerExpiredWakeCompletedPowerDownWaitForDirectedUp:0x5A3

### -field WdfDevStatePwrPolTimerExpiredWakeCompletedPowerDownDirectedTriggerDPR:0x5A4

### -field WdfDevStatePwrPolTimerExpiredWakeCapableUndoPowerDownWaitForDirectedUp:0x5A5

### -field WdfDevStatePwrPolWakeCapableUsbSSCompletedUndoWaitForDirectedUp:0x5A6

### -field WdfDevStatePwrPolTimerExpiredWakeCapableUsbSSDirectedDown:0x5A7

### -field WdfDevStatePwrPolWaitingArmedWakeInterruptFiredDuringPowerDownCheckDirected:0x5A8

### -field WdfDevStatePwrPolTimerExpiredWakeCompletedPowerDownCheckDirected:0x5A9

### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeSucceededCheckDirected:0x5AA

### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeSucceededWaitForDirectedUp:0x5AB

### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeSucceededTriggerDPR:0x5AC

### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeFailedCheckDirected:0x5AD

### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeFailedWaitForDirectedUp:0x5AE

### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeFailedTriggerDPR:0x5AF

### -field WdfDevStatePwrPolWaitingArmedDirectedDownWakeInterruptFiredTriggerDPR:0x5B0

### -field WdfDevStatePwrPolWaitingArmedDirectedDownWakeInterruptFired:0x5B1

### -field WdfDevStatePwrPolWaitingArmedDirectedDown:0x5B2

### -field WdfDevStatePwrPolWaitingArmedDirectedDownWakeSucceededCancelUsbSS:0x5B3

### -field WdfDevStatePwrPolWaitingArmedDirectedDownWakeFailedCancelUsbSS:0x5B4

### -field WdfDevStatePwrPolWaitingArmedDirectedDownTriggerDPR:0x5B5

### -field WdfDevStatePwrPolWaitingArmedDirectedDownWakeSucceededTriggerDPR:0x5B6

### -field WdfDevStatePwrPolWaitingArmedDirectedDownUsbSSCompleted:0x5B7

### -field WdfDevStatePwrPolWaitingArmedDirectedDownUsbSSCompletedTriggerDPR:0x5B8

### -field WdfDevStatePwrPolWaitingArmedDirectedDownWakeFailedCancelUsbSSTriggerDPR:0x5B9

### -field WdfDevStatePwrPolUsbSSCancelled:0x5BA

### -field WdfDevStatePwrPolTimerExpiredWakeCapableRevertArmWake:0x5BB

### -field WdfDevStatePwrPolSleepingWakeCancelWake:0x5BC

### -field WdfDevStatePwrPolSleepingWakeCancelWakeNP: 0x5BD | WdfDevStateNP

### -field WdfDevStatePwrPolSystemWakeDeviceD0PowerRequestFailed:0x5BE

### -field WdfDevStatePwrPolSystemWakeDevicePowerRequestFailed:0x5BF

### -field WdfDevStatePwrPolNull:0x5C0



## -remarks

The WDF_DEVICE_POWER_POLICY_STATE enumeration is used as a member type in the <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_notification_data">WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA</a> structure and as the return type for the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepowerpolicystate">WdfDeviceGetDevicePowerPolicyState</a> method.

