---
UID: NC:wdm.PCW_CALLBACK
title: PCW_CALLBACK (wdm.h)
description: Providers can implement a PCW_CALLBACK function to receive notification when consumers perform certain actions, such as adding or removing counters from a query.
old-location: devtest\pcwcallback.htm
tech.root: devtest
ms.assetid: 5058fc17-1016-45bc-a6ea-5e2458824e7b
ms.date: 02/23/2018
keywords: ["PCW_CALLBACK callback function"]
ms.keywords: PCW_CALLBACK, PCW_CALLBACK callback, PcwCallback, PcwCallback callback function [Driver Development Tools], devtest.pcwcallback, km_pcw_f4d70925-0361-4aa6-9e4b-3f1e00a01535.xml, wdm/PcwCallback
f1_keywords:
 - "wdm/PcwCallback"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- PcwCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCW\_CALLBACK callback function

## -description

Providers can optionally implement a `PCW_CALLBACK` function to receive notifications when consumers make requests such as enumerating instances or collecting counterset data. The [Performance Counter Library (PERFLIB version 2.0)](https://go.microsoft.com/fwlink/p/?linkid=144623) calls the `PCW_CALLBACK` function before completing the consumer's request.

## -parameters

### -param Type [in]

A [PCW\_CALLBACK\_TYPE](ne-wdm-_pcw_callback_type.md) enumeration value indicating why the callback was invoked. Possible values are `PcwCallbackAddCounter`, `PcwCallbackRemoveCounter`, `PcwCallbackEnumerateInstances`, and `PcwCallbackCollectData`.

### -param Info [in]

A pointer to a [PCW\_CALLBACK\_INFORMATION](ns-wdm-_pcw_callback_information.md) union that supplies details about why the provider callback was invoked. The details will be in the field corresponding to the `Type` parameter. For example, if `Type == PcwCallbackEnumerateInstances` then the details will be in `Info->EnumerateInstances`.

### -param Context [in, optional]

The callback context that was supplied by the provider when calling [PcwRegister](nf-wdm-pcwregister.md) or when calling the CTRPP-generated Register function (which invokes `PcwRegister`).

## -returns

The `PCW_CALLBACK` callback function should return `STATUS_SUCCESS` if the callback completed without errors, or an `NTSTATUS` error code otherwise. Note that this return code is for informational purposes only and that processing of the consumer's request will continue even if the callback returns an error.

## -remarks

Counterset providers can supply information to the consumer through two different systems:

- The provider can use `PcwCreateInstance` and `PcwCloseInstance` to maintain a list of available instances and the corresponding counter data. This system is simple to implement but limited in flexibility. When using this system, the provider does not need to supply a callback function. For more information on this system, refer to the documentation for [PcwCreateInstance](nf-wdm-pcwcreateinstance.md).
- The provider can supply a `PCW_CALLBACK` function that will be invoked by the Performance Counter Library as needed to collect data.

The callback implementation must be thread-safe. Multiple different consumers might simultaneously request data from the provider on different threads.

The callback must handle the `PcwCallbackEnumerateInstances` and `PcwCallbackCollectData` request types. The callback usually does not need to handle other request types, but in complex scenarios the callback might also handle `PcwCallbackAddCounter` and `PcwCallbackRemoveCounter` to optimize data collection (i.e. to disable statistics tracking when no queries are active).

The callback is responsible for generating `Name` and `Id` values for the counterset instances.

- Instance `Id` values MUST be stable over time (the same logical instance should use the same `Id` value for all invocations of the callback), should be unique (e.g. do not simply use 0 for all instances), and should be less than 0xFFFFFFFE (do not use `PCW_ANY_INSTANCE_ID`). When possible, the instance `Id` should be meaningful (e.g. a Process counterset might use a PID as the `Id`) instead of arbitrary (e.g. a sequence number).
- Instance `Name` values MUST be stable over time (the same logical instance should use the same `Name` value for all invocations of the callback) and MUST be unique. If the counterset supports multiple instances, the instance `Name` should not be blank. String matching is done using a case-insensitive comparison, so `Name` values should not differ only by case.

When handling `PcwCallbackCollectData` requests, a basic callback implementation will simply invoke [PcwAddInstance](nf-wdm-pcwaddinstance.md) (or the CTRPP-generated Add\*\*\*) once for each counterset instance. The following optimizations may be used in more advanced implementations when necessary:

- If `Info->CollectData.CounterMask != (UINT64)-1` then the consumer does not need all of the counters in the counterset. In this case, the callback may optimize data collection by leaving the corresponding values as 0 in the counter data block.
- If `Info->CollectData.InstanceId != PCW_ANY_INSTANCE_ID` then the consumer only wants data about instances with an `InstanceId` equal to `CollectData.InstanceId`. The callback may optimize data collection by skipping the call to `PcwAddInstance` for instances with non-matching `InstanceId`.
- If `Info->CollectData.InstanceMask != "*"` then the consumer only wants data about instances with an `InstanceName` that matches the wildcard pattern of `CollectData.InstanceMask`. The callback may optimize data collection by skipping the call to `PcwAddInstance` for instances with non-matching `InstanceName`. Wildcard matching is hard to implement correctly, so this optimization is recommended only when instance data collection is very expensive.

In most cases, the callback implementation for a `PcwCallbackEnumerateInstances` request will be identical to the implementation for a `PcwCallbackCollectData`. The callback may optionally optimize data collection by omitting the actual counter data in the call to `PcwAddInstance` (i.e. by passing 0 and NULL for the `Count` and `Data` parameters).

A callback implementation could be structured as follows:

```C
NTSTATUS NTAPI
MyProviderCallback(
    _In_ PCW_CALLBACK_TYPE Type,
    _In_ PPCW_CALLBACK_INFORMATION Info,
    _In_opt_ PVOID Context)
{
    PCW_MASK_INFORMATION* MaskInfo;
    PAGED_CODE();

    switch (Type)
    {
    case PcwCallbackCollectData:
        MaskInfo = &Info->CollectData;
        break;

    case PcwCallbackEnumerateInstances:
        MaskInfo = &Info->EnumerateInstances;
        break;

    case PcwCallbackAddCounter:
        // Optional (for optimizing data collection):
        // InterlockedIncrement(&CollectionEnableCount);
        return STATUS_SUCCESS; // Normally no action needed.

    case PcwCallbackRemoveCounter:
        // Optional (for optimizing data collection):
        // InterlockedDecrement(&CollectionEnableCount);
        return STATUS_SUCCESS; // Normally no action needed.
    }

    // Common code for CollectData and EnumerateInstances.
    // Note that this code needs to be thread-safe, as multiple
    // threads might invoke this callback at the same time.

    for (Instance : InstanceList) { // Pseudocode, need thread-safe enumeration
        NTSTATUS Status;

        // Optional optimization:
        // if (MaskInfo->InstanceId != PCW_ANY_INSTANCE_ID && Instance->Id != MaskInfo->InstanceId) {
        //     continue;
        // }

        // Note that in most cases, you'll use a CTRPP-generated Add wrapper instead of directly
        // calling PcwAddInstance.
        Status = PcwAddInstance(MaskInfo->Buffer,
                                &Instance->Name,
                                Instance->Id,
                                1, // Number of items in PcwData array
                                &Instance->PcwData);
        if (!NT_SUCCESS(Status)) {
            return Status;
        }
    }

    return STATUS_SUCCESS;
}
```

### - example

Most counterset providers use the [CTRPP](/windows/win32/perfctrs/ctrpp) tool to process their counterset manifest and generate helper functions, including functions wrapping `PcwRegister` (CTRPP generates the counter descriptors) and `PcwAddInstance` (CTRPP generates code for wrapping the provider's data structures into the format required by `PcwAddInstance`).

For reference in this example, the following is the CTRPP-generated Register function for the `KCS.man` manifest from the KCS sample.

```C
EXTERN_C FORCEINLINE NTSTATUS
KcsRegisterGeometricWave(
    __in_opt PPCW_CALLBACK Callback,
    __in_opt PVOID CallbackContext
    )
{
    PCW_REGISTRATION_INFORMATION RegInfo;
    UNICODE_STRING Name = RTL_CONSTANT_STRING(L"Geometric Waves");
    PCW_COUNTER_DESCRIPTOR Descriptors[] = {
        { 1, 0, FIELD_OFFSET(GEOMETRIC_WAVE_VALUES, Triangle), RTL_FIELD_SIZE(GEOMETRIC_WAVE_VALUES, Triangle)},
        { 2, 0, FIELD_OFFSET(GEOMETRIC_WAVE_VALUES, Square), RTL_FIELD_SIZE(GEOMETRIC_WAVE_VALUES, Square)},
    };

    PAGED_CODE();

    RtlZeroMemory(&RegInfo, sizeof RegInfo);

    RegInfo.Version = PCW_CURRENT_VERSION;
    RegInfo.Counters = Descriptors;
    RegInfo.CounterCount = RTL_NUMBER_OF(Descriptors);
    RegInfo.Callback = Callback;
    RegInfo.CallbackContext = CallbackContext;
    RegInfo.Name = &Name;

    return PcwRegister(&KcsGeometricWave, &RegInfo);
}
```

The counterset provider implements the `PCW_CALLBACK` function to handle consumer requests. The following code example shows a `PCW_CALLBACK` function named `KcsGeometricWaveCallback` that enumerates and collects simulated data. (Note that `KcsAddGeometricWave` is a CTRPP-generated helper function that calls `PcwAddInstance`.)

```C
NTSTATUS
KcsAddGeometricInstance (
    _In_ PPCW_BUFFER Buffer,
    _In_ PCWSTR Name,
    _In_ ULONG Id,
    _In_ ULONG MinimalValue,
    _In_ ULONG Amplitude
    )
{
    ULONG Index;
    LARGE_INTEGER Timestamp;
    UNICODE_STRING UnicodeName;
    GEOMETRIC_WAVE_VALUES Values;

    PAGED_CODE();

    KeQuerySystemTime(&Timestamp);

    Index = (Timestamp.QuadPart / 10000000) % 10;

    Values.Triangle = MinimalValue + Amplitude * abs(5 - Index) / 5;
    Values.Square = MinimalValue + Amplitude * (Index < 5);

    RtlInitUnicodeString(&UnicodeName, Name);

    return KcsAddGeometricWave(Buffer, &UnicodeName, Id, &Values);
}

NTSTATUS NTAPI
KcsGeometricWaveCallback (
    __in PCW_CALLBACK_TYPE Type,
    __in PPCW_CALLBACK_INFORMATION Info,
    __in_opt PVOID Context
    )
{
    NTSTATUS Status;
    UNICODE_STRING UnicodeName;

    UNREFERENCED_PARAMETER(Context);

    PAGED_CODE();

    switch (Type) {
    case PcwCallbackEnumerateInstances:

        //
        // Instances are being enumerated, so we add them without values.
        //

        RtlInitUnicodeString(&UnicodeName, L"Small Wave");
        Status = KcsAddGeometricWave(Info->EnumerateInstances.Buffer,
                                     &UnicodeName,
                                     0,
                                     NULL);
        if (!NT_SUCCESS(Status)) {
            return Status;
        }

        RtlInitUnicodeString(&UnicodeName, L"Medium Wave");
        Status = KcsAddGeometricWave(Info->EnumerateInstances.Buffer,
                                     &UnicodeName,
                                     1,
                                     NULL);
        if (!NT_SUCCESS(Status)) {
            return Status;
        }

        RtlInitUnicodeString(&UnicodeName, L"Large Wave");
        Status = KcsAddGeometricWave(Info->EnumerateInstances.Buffer,
                                     &UnicodeName,
                                     2,
                                     NULL);
        if (!NT_SUCCESS(Status)) {
            return Status;
        }

        break;

 case PcwCallbackCollectData:

        //
        // Add values for 3 instances of Geometric Wave Counter Set.
        //

        Status = KcsAddGeometricInstance(Info->CollectData.Buffer,
                                         L"Small Wave",
                                         0,
                                         40,
                                         20);
        if (!NT_SUCCESS(Status)) {
            return Status;
        }

        Status = KcsAddGeometricInstance(Info->CollectData.Buffer,
                                         L"Medium Wave",
                                         1,
                                         30,
                                         40);
        if (!NT_SUCCESS(Status)) {
            return Status;
        }

        Status = KcsAddGeometricInstance(Info->CollectData.Buffer,
                                         L"Large Wave",
                                         2,
                                         20,
                                         60);
        if (!NT_SUCCESS(Status)) {
            return Status;
        }

        break;
    }

    return STATUS_SUCCESS;
}
```

In the `DriverEntry` routine of the KCS sample, the `KcsGeometricWaveCallback` function is specified as the `Callback` when `KcsRegisterGeometricWave` registers the counter set.

```C
    //
    // Register Countersets during DriverEntry. (TODO: Unregister at driver unload.)
    //

    Status = KcsRegisterGeometricWave(KcsGeometricWaveCallback, NULL);
    if (!NT_SUCCESS(Status)) {
        return Status;
    }
```

## -see-also

[PcwRegister function](nf-wdm-pcwregister.md)

[PcwAddInstance function](nf-wdm-pcwaddinstance.md)

[PcwCreateInstance function](nf-wdm-pcwcreateinstance.md)

[\_PCW\_CALLBACK\_TYPE enumeration](ne-wdm-_pcw_callback_type.md)

[\_PCW\_CALLBACK\_INFORMATION structure](ns-wdm-_pcw_callback_information.md)

[CTRPP](/windows/win32/perfctrs/ctrpp)

[Performance Counter Library (PERFLIB version 2.0)](https://go.microsoft.com/fwlink/p/?linkid=144623)
