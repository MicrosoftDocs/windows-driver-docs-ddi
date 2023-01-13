---
UID: NF:wdm.PoRegisterPowerSettingCallback
title: PoRegisterPowerSettingCallback function (wdm.h)
description: The PoRegisterPowerSettingCallback routine in wdm.h registers a power-setting callback routine to receive notifications of changes in the specified power setting.
tech.root: kernel
ms.date: 01/10/2023
keywords: ["PoRegisterPowerSettingCallback function"]
ms.keywords: PoRegisterPowerSettingCallback, PoRegisterPowerSettingCallback routine [Kernel-Mode Driver Architecture], kernel.poregisterpowersettingcallback, portn_ddaef830-5cf5-4b7f-9fa6-e29a2b9f847f.xml, wdm/PoRegisterPowerSettingCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - PoRegisterPowerSettingCallback
 - wdm/PoRegisterPowerSettingCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoRegisterPowerSettingCallback
---

## -description

The **PoRegisterPowerSettingCallback** routine registers a power-setting callback routine to receive notifications of changes in the specified power setting.

## -parameters

### -param DeviceObject [in, optional]

A pointer to a [DEVICE_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object) structure that is associated with the caller of this routine. This parameter is optional. It is used internally only for debugging purposes. If this parameter is not supplied, it must be set to **NULL**.

### -param SettingGuid [in]

A pointer to the GUID that represents the power setting for this registration. When the specified power setting changes, the power manager calls the callback routine to notify the driver of the change and to supply the new value of the setting. For more information, see Remarks.

### -param Callback [in]

A pointer to a caller-implemented power-setting callback routine that the power manager calls when the specified power setting changes. For the functional prototype for the callback routine, see [Power-Setting Callback](/).

### -param Context [in, optional]

A pointer to the context for the callback routine. This parameter is optional. It is provided so that a driver or device context can be passed to the callback routine. If this parameter is not used, it must be set to **NULL**.

### -param Handle [out]

A handle that the power manager uses to represent the callback routine. A driver must subsequently supply this handle in a call to [PoUnregisterPowerSettingCallback](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pounregisterpowersettingcallback) to unregister the callback routine.

## -returns

**PoRegisterPowerSettingCallback** returns one of the following:

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The routine registered the callback routine. |
| **STATUS_INSUFFICIENT_RESOURCES** | The routine could not allocate the system resources that are required to register the callback routine. |

## -remarks

A driver calls **PoRegisterPowerSettingCallback** to register a callback routine with the power manager. The power manager subsequently calls this callback routine to notify the driver after there is a change to the specified power setting. In addition, the power manager initializes the power setting of the driver by immediately calling the callback routine and passing the current value of the power setting. The power manager initializes the power setting of the driver this way regardless of whether the power setting has actually changed.

A driver should call **PoRegisterPowerSettingCallback** for each power setting that the driver needs to monitor. Drivers should call this routine in their [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine during initialization. Typically, most drivers pass a pointer to a device extension in the *Context* parameter.

To unregister a power-setting callback, call the [PoUnregisterPowerSettingCallback](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pounregisterpowersettingcallback) routine.

Typically, Kernel-Mode Driver Framework (KMDF) drivers should call **PoRegisterPowerSettingCallback** from their [EvtDeviceSelfManagedIoInit](/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init) callback function, and should call **PoUnregisterPowerSettingCallback** from their [EvtDeviceSelfManagedIoCleanup](/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup) callback function. These drivers should not call **PoRegisterPowerSettingCallback** from their [EvtDriverDeviceAdd](/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add) callback function; otherwise, the power-setting callback routine might be called before the driver stack is completely built.

The callback routine that is registered for a particular power setting is called when a transition in power state occurs that changes the value of the setting, or when the power manager changes the value of the setting. For example, if *SettingGuid* points to the GUID value GUID_LIDSWITCH_STATE_CHANGE, the callback routine is called when the lid to a laptop computer clicks open or closed. The *Value* parameter passed to the callback routine in this example points to a ULONG value that is 1 if the state of the lid switch changed from closed to open, and is 0 if the state of the lid switch changed from open to closed. For more information, see the power-setting GUID definitions and extensive comments in the Wdm.h header file.

The initial call to a callback routine might occur immediately, before the **PoRegisterPowerSettingCallback** call that registers the routine returns.

**PoRegisterPowerSettingCallback** can be called only at IRQL = PASSIVE_LEVEL.

### Power-Setting Callback

The function prototype of the power-setting callback routine is as follows:

```cpp
NTSTATUS
POWER_SETTING_CALLBACK (
  _In_ LPCGUID SettingGuid,
  _In_ PVOID Value,
  _In_ ULONG ValueLength,
  _Inout_opt_ PVOID Context
);
```

The power-setting callback parameters are:

**SettingGuid**  
A pointer to a GUID that represents the power setting that changed. Power settings and their corresponding GUIDs are defined in Wdm.h.

**Value**  
A pointer to the new value of the power setting that changed.

**ValueLength**  
A value of type ULONG that specifies the size, in bytes, of the new power setting value.

**Context**  
The pointer to the context that a driver supplied in the call to **PoRegisterPowerSettingCallback** that registered the callback routine.

The power manager calls a power-setting callback at IRQL = PASSIVE_LEVEL.

#### Examples

To define a power-setting callback routine, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a power-setting callback routine that is named `MyPowerSettingCallback`, use the POWER_SETTING_CALLBACK type as shown in this code example:

```cpp
POWER_SETTING_CALLBACK MyPowerSettingCallback;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
NTSTATUS
  MyPowerSettingCallback(
    LPCGUID SettingGuid,
    PVOID Value,
    ULONG ValueLength,
    PVOID Context 
    )
  {
      // Function body
  }
```

The POWER_SETTING_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the POWER_SETTING_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver)

[EvtDeviceSelfManagedIoCleanup](/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup)

[EvtDeviceSelfManagedIoInit](/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init)

[EvtDriverDeviceAdd](/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add)

[PoUnregisterPowerSettingCallback](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pounregisterpowersettingcallback)
