---
UID: NA:wdfinterrupt
ms.assetid: d693610e-50f5-3bb7-9cb0-aed7080ca4dd
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfinterrupt.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfinterrupt.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_INTERRUPT_CONFIG_INIT function](nf-wdfinterrupt-wdf_interrupt_config_init.md) | The WDF_INTERRUPT_CONFIG_INIT function initializes a WDF_INTERRUPT_CONFIG structure. |
| [WDF_INTERRUPT_EXTENDED_POLICY_INIT function](nf-wdfinterrupt-wdf_interrupt_extended_policy_init.md) | The WDF_INTERRUPT_EXTENDED_POLICY_INIT function initializes a WDF_INTERRUPT_EXTENDED_POLICY structure. |
| [WDF_INTERRUPT_INFO_INIT function](nf-wdfinterrupt-wdf_interrupt_info_init.md) | The WDF_INTERRUPT_INFO_INIT function initializes a WDF_INTERRUPT_INFO structure. |
| [WdfInterruptCreate function](nf-wdfinterrupt-wdfinterruptcreate.md) | The WdfInterruptCreate method creates a framework interrupt object. |
| [WdfInterruptDisable function](nf-wdfinterrupt-wdfinterruptdisable.md) | The WdfInterruptDisable method disables a specified device interrupt by calling the driver's EvtInterruptDisable callback function. |
| [WdfInterruptEnable function](nf-wdfinterrupt-wdfinterruptenable.md) | The WdfInterruptEnable method enables a specified device interrupt by calling the driver's EvtInterruptEnable callback function. |
| [WdfInterruptGetDevice function](nf-wdfinterrupt-wdfinterruptgetdevice.md) | The WdfInterruptGetDevice method returns a handle to the framework device object that is associated with a specified framework interrupt object. |
| [WdfInterruptGetInfo function](nf-wdfinterrupt-wdfinterruptgetinfo.md) | The WdfInterruptGetInfo method retrieves information about a specified interrupt. |
| [WdfInterruptQueueDpcForIsr function](nf-wdfinterrupt-wdfinterruptqueuedpcforisr.md) | The WdfInterruptQueueDpcForIsr method queues a framework interrupt object's EvtInterruptDpc callback function for execution. |
| [WdfInterruptQueueWorkItemForIsr function](nf-wdfinterrupt-wdfinterruptqueueworkitemforisr.md) | The WdfInterruptQueueWorkItemForIsr method queues a framework interrupt object's EvtInterruptWorkItem callback function for execution. |
| [WdfInterruptReportActive function](nf-wdfinterrupt-wdfinterruptreportactive.md) | The WdfInterruptReportActive informs the system that the interrupt is active and the driver is ready to process interrupt requests on the associated lines. |
| [WdfInterruptReportInactive function](nf-wdfinterrupt-wdfinterruptreportinactive.md) | The WdfInterruptReportInactive method informs the system that the interrupt is no longer active and the driver is not expecting interrupt requests on the associated lines. |
| [WdfInterruptSetExtendedPolicy function](nf-wdfinterrupt-wdfinterruptsetextendedpolicy.md) | The WdfInterruptSetExtendedPolicy method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt. |
| [WdfInterruptSetPolicy function](nf-wdfinterrupt-wdfinterruptsetpolicy.md) | The WdfInterruptSetPolicy method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt. |
| [WdfInterruptSynchronize function](nf-wdfinterrupt-wdfinterruptsynchronize.md) | The WdfInterruptSynchronize method executes a specified callback function at the device's DIRQL while holding an interrupt object's spin lock. |
| [WdfInterruptTryToAcquireLock function](nf-wdfinterrupt-wdfinterrupttrytoacquirelock.md) | The WdfInterruptTryToAcquireLock method attempts to acquire an interrupt object's passive lock. |
| [WdfInterruptWdmGetInterrupt function](nf-wdfinterrupt-wdfinterruptwdmgetinterrupt.md) | The WdfInterruptWdmGetInterrupt method returns a pointer to the WDM interrupt object that is associated with a specified framework interrupt object. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_WDF_INTERRUPT_DISABLE callback](nc-wdfinterrupt-evt_wdf_interrupt_disable.md) | A driver's EvtInterruptDisable event callback function disables a specified hardware interrupt. |
| [EVT_WDF_INTERRUPT_DPC callback](nc-wdfinterrupt-evt_wdf_interrupt_dpc.md) | A driver's EvtInterruptDpc event callback function processes interrupt information that the driver's EvtInterruptIsr callback function has stored. |
| [EVT_WDF_INTERRUPT_ENABLE callback](nc-wdfinterrupt-evt_wdf_interrupt_enable.md) | A driver's EvtInterruptEnable event callback function enables a specified hardware interrupt. |
| [EVT_WDF_INTERRUPT_ISR callback](nc-wdfinterrupt-evt_wdf_interrupt_isr.md) | A driver's EvtInterruptIsr event callback function services a hardware interrupt. |
| [EVT_WDF_INTERRUPT_SYNCHRONIZE callback](nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md) | A driver's EvtInterruptSynchronize event callback function performs operations that must be synchronized with an EvtInterruptIsr callback function. |
| [EVT_WDF_INTERRUPT_WORKITEM callback](nc-wdfinterrupt-evt_wdf_interrupt_workitem.md) | A driver's EvtInterruptWorkItem event callback function processes interrupt information that the driver's EvtInterruptIsr callback function has stored. |
| [PFN_WDFINTERRUPTACQUIRELOCK callback](nc-wdfinterrupt-pfn_wdfinterruptacquirelock.md) | The WdfInterruptAcquireLock method begins a code sequence that executes at the device's device interrupt request level (DIRQL) while holding an interrupt object's spin lock. |
| [PFN_WDFINTERRUPTRELEASELOCK callback](nc-wdfinterrupt-pfn_wdfinterruptreleaselock.md) | The WdfInterruptReleaseLock method ends a code sequence that executes at the device's DIRQL while holding an interrupt object's spin lock. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_INTERRUPT_CONFIG structure](ns-wdfinterrupt-_wdf_interrupt_config.md) | The WDF_INTERRUPT_CONFIG structure contains configuration information for a device interrupt. |
| [_WDF_INTERRUPT_EXTENDED_POLICY structure](ns-wdfinterrupt-_wdf_interrupt_extended_policy.md) | The WDF_INTERRUPT_EXTENDED_POLICY structure contains information about an interrupt's policy, priority, affinity, and group. |
| [_WDF_INTERRUPT_INFO structure](ns-wdfinterrupt-_wdf_interrupt_info.md) | The WDF_INTERRUPT_INFO structure contains information about a device's interrupt resource. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDF_INTERRUPT_POLARITY enumeration](ne-wdfinterrupt-_wdf_interrupt_polarity.md) | The WDF_INTERRUPT_POLARITY enumeration type is used to specify an interrupt signal's polarity. |
| [_WDF_INTERRUPT_POLICY enumeration](ne-wdfinterrupt-_wdf_interrupt_policy.md) | The WDF_INTERRUPT_POLICY enumeration type identifies the affinity policies that the PnP manager can use when it assigns a device's interrupts to the processors of a multiprocessor system. |
| [_WDF_INTERRUPT_PRIORITY enumeration](ne-wdfinterrupt-_wdf_interrupt_priority.md) | The WDF_INTERRUPT_PRIORITY enumeration type identifies relative priorities for device interrupts. |
