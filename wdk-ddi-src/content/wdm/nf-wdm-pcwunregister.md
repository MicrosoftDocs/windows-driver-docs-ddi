---
UID: NF:wdm.PcwUnregister
title: PcwUnregister function (wdm.h)
description: The PcwUnregister function unregisters the provider of the specified counter set.
old-location: devtest\pcwunregister.htm
tech.root: devtest
ms.assetid: cf6aeb30-732b-494c-a714-caa6326c0375
ms.date: 07/28/2020
keywords: ["PcwUnregister function"]
ms.keywords: PcwUnregister, PcwUnregister function [Driver Development Tools], devtest.pcwunregister, km_pcw_842b91a3-a846-4d1c-adcd-7e1b3fdf4af5.xml, wdm/PcwUnregister
f1_keywords:
 - "wdm/PcwUnregister"
 - "PcwUnregister"
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
- PcwUnregister
targetos: Windows
req.typenames: 
---

# PcwUnregister function

## -description

The `PcwUnregister` function closes the specified counterset registration. Most developers will use a [CTRPP](https://docs.microsoft.com/windows/win32/perfctrs/ctrpp)-generated Unregister\*\*\* function instead of calling this function directly.

## -parameters

### -param Registration [in]

A pointer to the registration being closed.

## -remarks

The `PcwUnregister` function closes the specified counterset registration. Instances owned by the counterset registration are automatically closed. These instances should not be accessed by the provider while the counter set is being unregistered or after the counter set is unregistered.

Before the provider uses this function, the provider must call the [PcwRegister](nf-wdm-pcwregister.md) function to create a registration.

### CTRPP-generated Unregister\*\*\* function

Most developers do not need to call `PcwUnregister` directly. Instead, they will compile a manifest with the CTRPP tool and use the Unregister\*\*\* function from the CTRPP-generated header. The generated function will look like this:

```C
EXTERN_C FORCEINLINE VOID
UnregisterMyCounterset(
    VOID
    )
{
    PAGED_CODE();

    PcwUnregister(MyCounterset);
}
```

The CTRPP-generated Unregister function will be named *Prefix*Unregister*CounterSet*. *Prefix* is usually blank, but may be present if the `-prefix` parameter was used on the CTRPP command-line. *CounterSet* is the name of the counterset, as specified in the manifest. Note that the function references `MyCounterset`, which is a global variable that holds the counterset registration handle initialized by the CTRPP-generated Register\*\*\* function.

## -see-also

[PcwRegister function](nf-wdm-pcwregister.md)
