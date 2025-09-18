---
UID: NF:wdftimer.WdfTimerCreate
title: WdfTimerCreate function (wdftimer.h)
description: The WdfTimerCreate method creates a framework timer object.
old-location: wdf\wdftimercreate.htm
tech.root: wdf
ms.date: 09/18/2025
keywords: ["WdfTimerCreate function"]
ms.keywords: DFTimerObjectRef_3388a92e-119d-4208-9cf5-2c934435ff25.xml, WdfTimerCreate, WdfTimerCreate method, kmdf.wdftimercreate, wdf.wdftimercreate, wdftimer/WdfTimerCreate
req.header: wdftimer.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfTimerCreate
 - wdftimer/WdfTimerCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfTimerCreate
---

# WdfTimerCreate function

## -description

*[Applies to KMDF and UMDF]*

The **WdfTimerCreate** method creates a framework timer object.

## -parameters

### -param Config [in]

A pointer to a [WDF_TIMER_CONFIG](/windows-hardware/drivers/ddi/wdftimer/ns-wdftimer-_wdf_timer_config) structure.

### -param Attributes [in]

A pointer to a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that contains object attributes for the new timer object.

### -param Timer [out]

A pointer to a location that receives a handle to the new framework timer object.

## -returns

**WdfTimerCreate** returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

| Return code | Description |
|-------------|-------------|
| **STATUS_WDF_PARENT_NOT_SPECIFIED** | The *Attributes* parameter was **NULL**, or the **ParentObject** member of the [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that *Attributes* specifies was **NULL**. |
| **STATUS_INVALID_PARAMETER** | An invalid parameter was specified. |
| **STATUS_INVALID_DEVICE_REQUEST** | The **ParentObject** member of the [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure did not reference a framework device object or an object whose chain of parents leads to a framework device object. |
| **STATUS_INSUFFICIENT_RESOURCES** | There was insufficient memory. |
| **STATUS_WDF_INCOMPATIBLE_EXECUTION_LEVEL** | The **AutomaticSerialization** member of the [WDF_TIMER_CONFIG](/windows-hardware/drivers/ddi/wdftimer/ns-wdftimer-_wdf_timer_config) structure was set to **TRUE**, but the parent device object's [execution level](/windows-hardware/drivers/ddi/wdfobject/ne-wdfobject-_wdf_execution_level) was set to **WdfExecutionLevelPassive**. |

For a list of other return values that the **WdfTimerCreate** method might return, see [Framework Object Creation Errors](/windows-hardware/drivers/wdf/framework-object-creation-errors).

This method might also return other [NTSTATUS values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

When your driver calls **WdfTimerCreate**, it must supply a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure and must specify a parent object in the structure's **ParentObject** member. The parent object can be a framework device object or any object whose chain of parents leads to a framework device object. The framework will delete the timer object when it deletes the device object.

After creating a timer object, the driver must call [WdfTimerStart](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimerstart) to start the timer's clock regardless of whether the timer is periodic or not.

If your driver provides [EvtCleanupCallback](/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup) or [EvtDestroyCallback](/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy) callback functions for the framework timer object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about framework timer objects, see [Using Timers](/windows-hardware/drivers/wdf/using-timers).

### Examples

The following code example initializes a [WDF_TIMER_CONFIG](/windows-hardware/drivers/ddi/wdftimer/ns-wdftimer-_wdf_timer_config) structure and a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure and then calls **WdfTimerCreate**.

```cpp
WDF_TIMER_CONFIG  timerConfig;
WDF_OBJECT_ATTRIBUTES  timerAttributes;
WDFTIMER  timerHandle;
NTSTATUS  status;

WDF_TIMER_CONFIG_INIT(
                      &timerConfig,
                      MyEvtTimerFunc
                      );

// Consider allowing a tolerance for the due time and period.
// For more information on high-resolution timers and timer coalescing, see:
// https://learn.microsoft.com/windows-hardware/drivers/kernel/high-resolution-timers
timerConfig.TolerableDelay = 10;

WDF_OBJECT_ATTRIBUTES_INIT(&timerAttributes);
timerAttributes.ParentObject = DeviceHandle;

status = WdfTimerCreate(
                        &timerConfig,
                        &timerAttributes,
                        &timerHandle
                        );

if (!NT_SUCCESS(status)) {
    return status;
}
```

## -see-also

- [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes)
- [WDF_OBJECT_ATTRIBUTES_INIT](/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init)
- [WDF_TIMER_CONFIG](/windows-hardware/drivers/ddi/wdftimer/ns-wdftimer-_wdf_timer_config)
- [WDF_TIMER_CONFIG_INIT](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdf_timer_config_init)
- [WdfTimerStart](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimerstart)
