---
UID: NF:wdm.PcwCloseInstance
title: PcwCloseInstance function (wdm.h)
description: The PcwCloseInstance function closes the specified instance of the counter set.
old-location: devtest\pcwcloseinstance.htm
tech.root: devtest
ms.assetid: a577a116-9e5e-42d3-aac0-a6b90131ad9d
ms.date: 02/23/2018
keywords: ["PcwCloseInstance function"]
ms.keywords: PcwCloseInstance, PcwCloseInstance function [Driver Development Tools], devtest.pcwcloseinstance, km_pcw_f30288bf-ff25-46fd-b058-74294fc03278.xml, wdm/PcwCloseInstance
f1_keywords:
 - "wdm/PcwCloseInstance"
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
- PcwCloseInstance
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcwCloseInstance function

## -description

The `PcwCloseInstance` function closes a counterset instance that was created using [PcwCreateInstance](nf-wdm-pcwcreateinstance.md). Most developers will use a [CTRPP](/windows/win32/perfctrs/ctrpp)-generated Close\*\*\* function instead of calling this function directly.

## -parameters

### -param Instance [in]

A pointer to the counterset instance to close.

## -remarks

Use the `PcwCreateInstance` function to create a counterset instance.

You cannot call `PcwCloseInstance` on an instance if you have already called [PcwUnregister](nf-wdm-pcwunregister.md) for the corresponding counterset registration. When you unregister the counterset, any remaining instances are closed for you. Closing them again will crash the system.

### CTRPP-generated Close\*\*\* function

Most developers do not need to call `PcwCloseInstance` directly. Instead, they will compile a manifest with the CTRPP tool and use the Close\*\*\* function from the CTRPP-generated header. The generated function will look like this:

```C
EXTERN_C FORCEINLINE VOID
CloseMyCounterset(
    __in PPCW_INSTANCE Instance
    )
{
    PAGED_CODE();

    PcwCloseInstance(Instance);
}
```

The CTRPP-generated Close function will be named *Prefix*Close*CounterSet*. *Prefix* is usually blank, but may be present if the `-prefix` parameter was used on the CTRPP command-line. *CounterSet* is the name of the counterset, as specified in the manifest.

## -see-also

[PcwCreateInstance function](nf-wdm-pcwcreateinstance.md)
