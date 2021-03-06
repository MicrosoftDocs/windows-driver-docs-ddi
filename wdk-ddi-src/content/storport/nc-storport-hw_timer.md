---
UID: NC:storport.HW_TIMER
title: HW_TIMER (storport.h)
description: The HwStorTimer routine is called after the interval that is specified when the miniport driver called StorPortNotification with the RequestTimerCall NotificationType value.
old-location: storage\hwstortimer.htm
tech.root: storage
ms.date: 04/01/2021
keywords: ["HW_TIMER callback function"]
ms.keywords: HW_TIMER, HwStorTimer, HwStorTimer routine [Storage Devices], storage.hwstortimer, stormini_6127daf5-8672-4bf4-9241-b67bed14b8f8.xml, storport/HwStorTimer
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_TIMER
 - storport/HW_TIMER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_TIMER
---

# HW_TIMER callback function

## -description

The **HwStorTimer** routine is called after the interval that is specified when the miniport driver called [**StorPortNotification**](../storport/nf-storport-storportnotification.md) with **RequestTimerCall** specified for the **NotificationType** parameter.

## -parameters

### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area.

## -remarks

The name **HwStorTimer** is only a placeholder. The actual prototype of this routine is defined in *Srb.h* as follows:

``` c
typedef
VOID
HW_TIMER (
  _In_ PVOID  DeviceExtension
  );
```

If the miniport opts into multi-channel support, the StartIo spin lock is still taken. However, if the miniport has requested multiple channel support via [**PERF_CONFIGURATION_DATA**](../storport/ns-storport-_perf_configuration_data.md), the StartIo spin lock is not taken or checked before the call to [**HwStorStartIo**](../storport/nc-storport-hw_startio.md) in the miniport. This means that the **HwStorStartIo** callback is not synchronized with the callback to the **HwStorTimer** routine when multi-channel support is used. The miniport must do this on its own by using a compiler interlocked intrinsic, for example using [**InterlockedCompareExchange**](../wdm/nf-wdm-interlockedcompareexchange.md).

A **HwStorTimer** routine is optional.

To define an **HwStorTimer** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorTimer** callback routine that is named **MyHwTimer**, use the following **HW_TIMER** type and implement your callback routine as follows:

``` c
HW_TIMER MyHwTimer;

_Use_decl_annotations_
VOID
MyHwTimer (
  _In_ PVOID  DeviceExtension
  );
  {
      ...
  }
```

The **HW_TIMER** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_TIMER** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[**StorPortNotification**](../storport/nf-storport-storportnotification.md)
