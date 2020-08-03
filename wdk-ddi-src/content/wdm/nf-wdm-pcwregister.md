---
UID: NF:wdm.PcwRegister
title: PcwRegister function (wdm.h)
description: The PcwRegister function registers the caller as a provider of the specified counter set.
old-location: devtest\pcwregister.htm
tech.root: devtest
ms.assetid: 40fdb77c-bd6b-4ecd-a9c8-fd5e5b2adc80
ms.date: 07/28/2020
keywords: ["PcwRegister function"]
ms.keywords: PcwRegister, PcwRegister function [Driver Development Tools], devtest.pcwregister, km_pcw_5204b626-3251-4c63-bd89-be1470980960.xml, wdm/PcwRegister
f1_keywords:
 - "wdm/PcwRegister"
 - "PcwRegister"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PcwRegister
targetos: Windows
req.typenames: 
---

# PcwRegister function

## -description

The `PcwRegister` function creates a new counterset registration. Most developers will use a [CTRPP](https://docs.microsoft.com/windows/win32/perfctrs/ctrpp)-generated Register\*\*\* function instead of calling this function directly.

## -parameters

### -param Registration [out]

A pointer to a PPCW\_REGISTRATION. Receives the handle to the new registration. The registration should be closed using [PcwUnregister](nf-wdm-pcwunregister.md).

### -param Info [in]

A pointer to a [PCW\_REGISTRATION\_INFORMATION](ns-wdm-_pcw_registration_information.md) structure that contains the details about the counter set being registered.

## -returns

`PcwRegister` returns one of the following values:

|Return code|Description
|---|---
|`STATUS_SUCCESS`|The counterset is successfully registered.
|`STATUS_INTEGER_OVERFLOW`|The number of the counters exposed by this registration exceeds the maximum supported.
|`STATUS_NO_MEMORY`|There is not enough space available to allocate memory for the counters.
|`STATUS_INVALID_PARAMETER_2`|A problem was found in the `Info` parameter. See below for some possible causes.

`PcwRegister` may return `STATUS_INVALID_PARAMETER_2` in the following cases:

- The `Info->Name->Length` field is 0 or is not a multiple of `sizeof(WCHAR)`.
- The `Info->Version` field does not match a supported value for this version of Windows. When running on Windows prior to 10.0.19645 (`NTDDI_VERSION < NTDDI_VERSION_MN`), the `Version` field must be set to PCW\_VERSION\_1 (0x100). When running on Windows 10.0.19645 and later (`NTDDI_VERSION >= NTDDI_VERSION_MN`), this may be set to PCW\_VERSION\_1 (0x100) or PCW\_VERSION\_2 (0x200).
- The `Info->Flags` field contains a value not recognized by the running version of Windows.

## -remarks

The provider calls this function to create a new counterset registration. All of the input arguments are captured so that the caller does not have to keep a copy of them.

By default, the new counterset is visible only to the server silo that was active at the time of registration (i.e. `PcwRegister` associates the newly-created registration with the server silo that was attached to the thread when `PcwRegister` is called). If running on Windows 10.0.19645 and later (`NTDDI_VERSION >= NTDDI_VERSION_MN`) you may create a counterset registration that is visible to all server silos by setting `PCW_REGISTRATION_INFORMATION::Version` to `PCW_VERSION_2` and setting `PCW_REGISTRATION_INFORMATION::Flags` to `PcwRegistrationSiloNeutral`.

### CTRPP-generated Register\*\*\* function

Most developers do not need to call `PcwRegister` directly. Instead, they will compile a manifest with the CTRPP tool and use the Register\*\*\* function from the CTRPP-generated header. The generated function will look like this:

```C
EXTERN_C FORCEINLINE NTSTATUS
RegisterMyCounterset(
    __in_opt PPCW_CALLBACK Callback,
    __in_opt PVOID CallbackContext
    )
{
    PCW_REGISTRATION_INFORMATION RegInfo;

    PAGED_CODE();

    InitRegistrationInformationMyCounterset(Callback, CallbackContext, &RegInfo);

    return PcwRegister(&MyCounterset, &RegInfo);
}
```

The CTRPP-generated Register function will be named *Prefix*Register*Counterset*. *Prefix* is usually blank, but may be present if the `-prefix` parameter was used on the CTRPP command-line. *Counterset* is the name of the counterset, as specified in the manifest. The generated Register function will invoke the *Prefix*InitRegistrationInformation*Counterset* function to initialize a `PCW_REGISTRATION_INFORMATION` structure and then invoke `PcwRegister` to create a new registration and store the handle in the global `MyCounterset` variable (declared in the CTRPP-generated header).

In some cases, the CTRPP-generated Add function might not be appropriate.

- If you must compile with `NTDDI_VERSION >= NTDDI_VERSION_FE` but must run on earlier versions of Windows, the CTRPP-generated Register function will not work because it sets `RegInfo.Version = PCW_CURRENT_VERSION`. When `NTDDI_VERSION >= NTDDI_VERSION_FE`, `PCW_CURRENT_VERSION` will be set to `PCW_VERSION_2`, causing `PcwRegister` to return an error.
- If you need to support multiple counterset registrations (e.g. to support a separate registration per server silo), the CTRPP-generated Register function will not work because it stores the returned handle in a global variable.
- If you want to create a silo-neutral counterset registration, the CTRPP-generated Register function will not work because there is no way to change the value of `RegInfo.Flags` before calling `PcwRegister`.

In these cases, use code like the following instead of calling the CTRPP-generated Register function:

```c
PCW_REGISTRATION_INFORMATION RegInfo;
InitRegistrationInformationMyCounterset(Callback, CallbackContext, &RegInfo);

// Modify RegInfo as needed,
// e.g. RegInfo.Version = PCW_VERSION_1,
// or RegInfo.Flags = PcwRegistrationSiloNeutral.

// If needed, use another variable to store the handle instead of MyCounterset.
Status = PcwRegister(&MyCounterset, &RegInfo);
```

The CTRPP-generated InitRegistrationInformation\*\*\* function initializes the `RegInfo` structure based on declarations from the manifest. For more information about the generated InitRegistrationInformation function, refer to the documentation for [PCW\_REGISTRATION\_INFORMATION](ns-wdm-_pcw_registration_information.md).

If using your own handle variables instead of `MyCounterset` to store the handle, you may also need to call `PcwUnregister` and `PcwCreateInstance` directly instead of using the CTRPP-generated `Unregister***` and `Create***` functions.

## -see-also

[PcwUnregister function](nf-wdm-pcwunregister.md)

[\_PCW\_REGISTRATION\_INFORMATION structure](ns-wdm-_pcw_registration_information.md)
