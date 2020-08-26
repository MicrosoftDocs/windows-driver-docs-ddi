---
UID: NS:wdm._PCW_REGISTRATION_INFORMATION
title: _PCW_REGISTRATION_INFORMATION (wdm.h)
description: The PCW_REGISTRATION_INFORMATION structure supplies details about the provider and the counter set.
old-location: devtest\pcw_registration_information.htm
tech.root: devtest
ms.assetid: f5305351-10b4-47e6-a8b6-e1a91c605ca9
ms.date: 07/28/2020
keywords: ["_PCW_REGISTRATION_INFORMATION structure"]
ms.keywords: "*PPCW_REGISTRATION_INFORMATION, PCW_REGISTRATION_INFORMATION, PCW_REGISTRATION_INFORMATION structure [Driver Development Tools], PPCW_REGISTRATION_INFORMATION, PPCW_REGISTRATION_INFORMATION structure pointer [Driver Development Tools], _PCW_REGISTRATION_INFORMATION, devtest.pcw_registration_information, km_pcw_a740182f-4844-4a98-9493-522087a3d27c.xml, wdm/PCW_REGISTRATION_INFORMATION, wdm/PPCW_REGISTRATION_INFORMATION"
f1_keywords:
 - "wdm/PCW_REGISTRATION_INFORMATION"
 - "PCW_REGISTRATION_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- PCW_REGISTRATION_INFORMATION
targetos: Windows
req.typenames: PCW_REGISTRATION_INFORMATION, *PPCW_REGISTRATION_INFORMATION
---

# _PCW_REGISTRATION_INFORMATION structure

## -description

The `PCW_REGISTRATION_INFORMATION` structure supplies details about the provider and the counter set. Most developers will use the [CTRPP](https://docs.microsoft.com/windows/win32/perfctrs/ctrpp)-generated Register\*\*\* or InitRegistrationInformation\*\*\* functions instead of using this structure directly.

## -struct-fields

### -field Version

The numeric value that specifies the version of Performance Counters for Windows (PCW) that the provider requires.

When running on Windows prior to 10.0.19645 (`NTDDI_VERSION < NTDDI_VERSION_MN`), the `Version` field must be set to PCW_VERSION_1 (0x100). When running on Windows 10.0.19645 and later (`NTDDI_VERSION >= NTDDI_VERSION_MN`), this may be set to PCW_VERSION_1 (0x100) or PCW_VERSION_2 (0x200). If the `Version` field is set to an unrecognized value, `PcwRegister` will return STATUS_INVALID_PARAMETER_2.

When using the CTRPP-generated Register\*\*\* or InitRegistrationInformation\*\*\* functions, the `Version` field will be set to `PCW_CURRENT_VERSION`, which is equivalent to one of the following values, depending on the compile-time value of `NTDDI_VERSION`:

|Condition|PCW_CURRENT_VERSION value
|---|---
|`NTDDI_VERSION <  NTDDI_WIN10_FE`|PCW_VERSION_1 (0x0100)
|`NTDDI_VERSION >= NTDDI_WIN10_FE`|PCW_VERSION_2 (0x0200)

If your code builds with `NTDDI_VERSION >= NTDDI_WIN10_FE` but needs to run on an earlier version of Windows, you will need to set `Version = PCW_VERSION_1` as described in the documentation for [PcwRegister](nf-wdm-pcwregister.md).

### -field Name

A pointer to the string that contains the name of the counterset to register. This string must not be NULL or blank.

Note that counterset name comparisons are not case-sensitive. If the same counterset name is used in two counterset registrations, consumers will collect data from both registrations.

### -field CounterCount

The number of descriptors provided in the `Counters` parameter.

### -field Counters

An array of descriptors for the counters of this counterset. The information from the descriptors will be used when extracting counter values from data blocks provided by calls to `PcwCreateInstance` or `PcwAddInstance`.

### -field Callback

A pointer to the optional [PCW_CALLBACK](nc-wdm-pcw_callback.md) callback function that notifies the provider about events related to this counter set. This field may be NULL if the callback is not needed (i.e. if the counterset instances will be managed via `PcwCreateInstance` and `PcwCloseInstance`).

### -field CallbackContext

A pointer value that will be passed to the provider-defined `PCW_CALLBACK` callback function each time it is invoked.

### -field Flags

The `Flags` field is only available when `NTDDI_VERSION >= NTDDI_WIN10_MN`.

The `Flags` field will be ignored if the `Version` field is less than `PCW_VERSION_2`.

The `Flags` field enables special behavior of `PcwRegister`. Set to a combination of one or more `PCW_REGISTRATION_FLAGS` values:

|PCW_REGISTRATION_FLAGS|Meaning
|---|---
|PcwRegistrationNone (0x0)        |Default (no special behaviors required).
|PcwRegistrationSiloNeutral (0x1) |Indicates that this registration should be visible to consumers in all server silos. By default, a registration is visible only to consumers in the server silo that was active when the registration was created (i.e. the registration that was attached to the thread when `PcwRegister` was called).

## -remarks

The [PcwRegister](nf-wdm-pcwregister.md) function takes an `Info` parameter that is a pointer to this structure.

### CTRPP-generated InitRegistrationInformation\*\*\* function

Most developers do not need to use `PCW_REGISTRATION_INFORMATION` directly. Instead, they will compile a manifest with the CTRPP tool and use the Register\*\*\* or InitRegistrationInformation\*\*\* functions from the CTRPP-generated header. The generated Register function calls InitRegistrationInformation and then calls `PcwRegister` (see [PcwRegister](nf-wdm-pcwregister.md) for details). The generated InitRegistrationInformation function will look like this:

```C
EXTERN_C FORCEINLINE VOID
InitRegistrationInformationMyCounterset(
    __in_opt PPCW_CALLBACK Callback,
    __in_opt PVOID CallbackContext,
    __out PCW_REGISTRATION_INFORMATION* RegInfo
    )
{
    static const UNICODE_STRING Name = RTL_CONSTANT_STRING(L"My Counterset Name");
    static const PCW_COUNTER_DESCRIPTOR Descriptors[] = {
        { 0, 0, FIELD_OFFSET(MY_COUNTER_DATA, MyData1), RTL_FIELD_SIZE(MY_COUNTER_DATA, MyData1)},
        { 1, 0, FIELD_OFFSET(MY_COUNTER_DATA, MyData2), RTL_FIELD_SIZE(MY_COUNTER_DATA, MyData2)},
    };

#if CTRPP_VERIFY_COUNTER_SIZES

    //
    // Verify that structure member size matches manifest counter size.
    //

    C_ASSERT(RTL_FIELD_SIZE(MY_COUNTER_DATA, MyData1) == sizeof(ULONGLONG));
    C_ASSERT(RTL_FIELD_SIZE(MY_COUNTER_DATA, MyData2) == sizeof(ULONG));

#endif // CTRPP_VERIFY_COUNTER_SIZES

    PAGED_CODE();

    RtlZeroMemory(RegInfo, sizeof(*RegInfo));
    RegInfo->Version = PCW_CURRENT_VERSION;
    RegInfo->Name = &Name;
    RegInfo->CounterCount = RTL_NUMBER_OF(Descriptors);
    RegInfo->Counters = (PCW_COUNTER_DESCRIPTOR*)Descriptors;
    RegInfo->Callback = Callback;
    RegInfo->CallbackContext = CallbackContext;
}
```

The CTRPP-generated InitRegistrationInformation function will be named *Prefix*InitRegistrationInformation*Counterset*. *Prefix* is usually blank, but may be present if the `-prefix` parameter was used on the CTRPP command-line. *Counterset* is the name of the counterset, as specified in the manifest. The generated InitRegistrationInformation function will initialize the provided `PCW_REGISTRATION_INFORMATION` structure with values from the function parameters and the manifest.

The CTRPP-generated InitRegistrationInformation function can optionally verify that the sizes of the structure members match the sizes declared in the manifest. By default, `CTRPP_VERIFY_COUNTER_SIZES` is set to 0, disabling this check. To enable this check, `#define CTRPP_VERIFY_COUNTER_SIZES 1` before including the CTRPP-generated header. If the check is enabled, a size mismatch will trigger a compile error due to failure of the C_ASSERT condition.

## -see-also

[_PCW_COUNTER_DESCRIPTOR structure](ns-wdm-_pcw_counter_descriptor.md)

[PCW_CALLBACK callback function](nc-wdm-pcw_callback.md)

[PcwRegister function](nf-wdm-pcwregister.md)

[CTRPP](https://docs.microsoft.com/windows/win32/perfctrs/ctrpp)
