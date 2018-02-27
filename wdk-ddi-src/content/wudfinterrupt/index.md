---
UID: NA:wudfinterrupt
ms.assetid: cbeea8a1-1f72-3eb6-bde5-b99d677f8a8d
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wudfinterrupt.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wudfinterrupt.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_INTERRUPT_EXTENDED_POLICY_INIT function](nf-wudfinterrupt-wdf_interrupt_extended_policy_init.md) | The WDF_INTERRUPT_EXTENDED_POLICY_INIT function initializes a WDF_INTERRUPT_EXTENDED_POLICY structure. |
| [WDF_INTERRUPT_INFO_INIT function](nf-wudfinterrupt-wdf_interrupt_info_init.md) | The WDF_INTERRUPT_INFO_INIT function initializes a WDF_INTERRUPT_INFO structure. |
| [WUDF_INTERRUPT_CONFIG_INIT function](nf-wudfinterrupt-wudf_interrupt_config_init.md) | The WUDF_INTERRUPT_CONFIG_INIT function initializes a WUDF_INTERRUPT_CONFIG structure. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [WUDF_INTERRUPT_DISABLE callback](nc-wudfinterrupt-wudf_interrupt_disable.md) | A driver's OnInterruptDisable event callback function disables a specified hardware interrupt. |
| [WUDF_INTERRUPT_ENABLE callback](nc-wudfinterrupt-wudf_interrupt_enable.md) | A driver's OnInterruptEnable event callback function enables a specified hardware interrupt. |
| [WUDF_INTERRUPT_ISR callback](nc-wudfinterrupt-wudf_interrupt_isr.md) | A driver's OnInterruptIsr event callback function services a hardware interrupt. |
| [WUDF_INTERRUPT_WORKITEM callback](nc-wudfinterrupt-wudf_interrupt_workitem.md) | A driver's OnInterruptWorkItem event callback function processes interrupt information that the driver's OnInterruptIsr callback function has stored. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_INTERRUPT_EXTENDED_POLICY structure](ns-wudfinterrupt-_wdf_interrupt_extended_policy.md) | The WDF_INTERRUPT_EXTENDED_POLICY structure contains information about an interrupt's policy, priority, affinity, and group. |
| [_WDF_INTERRUPT_INFO structure](ns-wudfinterrupt-_wdf_interrupt_info.md) | The WDF_INTERRUPT_INFO structure contains information about a device's interrupt resource. |
| [_WUDF_INTERRUPT_CONFIG structure](ns-wudfinterrupt-_wudf_interrupt_config.md) | The WUDF_INTERRUPT_CONFIG structure contains configuration information for a device interrupt. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDF_INTERRUPT_POLARITY enumeration](ne-wudfinterrupt-_wdf_interrupt_polarity.md) | The WDF_INTERRUPT_POLARITY enumeration type is used to specify an interrupt signal's polarity. |
| [_WDF_INTERRUPT_POLICY enumeration](ne-wudfinterrupt-_wdf_interrupt_policy.md) | The WDF_INTERRUPT_POLICY enumeration type identifies the affinity policies that the Plug and Play (PnP) manager can use when it assigns a device's interrupts to the processors of a multiprocessor system. |
| [_WDF_INTERRUPT_PRIORITY enumeration](ne-wudfinterrupt-_wdf_interrupt_priority.md) | The WDF_INTERRUPT_PRIORITY enumeration type identifies relative priorities for device interrupts. |
