---
UID: NF:wdm.IoIsWdmVersionAvailable
title: IoIsWdmVersionAvailable function (wdm.h)
description: The IoIsWdmVersionAvailable routine checks whether a given WDM version is supported by the operating system.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["IoIsWdmVersionAvailable function"]
ms.keywords: IoIsWdmVersionAvailable, IoIsWdmVersionAvailable routine [Kernel-Mode Driver Architecture], k104_775d6afa-6edd-4922-bdff-a8fe5d32bc3a.xml, kernel.ioiswdmversionavailable, wdm/IoIsWdmVersionAvailable
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoIsWdmVersionAvailable
 - wdm/IoIsWdmVersionAvailable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoIsWdmVersionAvailable
---

## -description

The **IoIsWdmVersionAvailable** routine checks whether a given WDM version is supported by the operating system.

## -parameters

### -param MajorVersion [in]

Specifies the major version number of WDM that is requested.

### -param MinorVersion [in]

Specifies the minor version number of WDM that is requested.

## -returns

**IoIsWdmVersionAvailable** returns **TRUE** if the version of WDM that the operating system provides is greater than or equal to the version number of WDM being requested. Otherwise, it returns **FALSE**.

## -remarks

Drivers should use the [RtlIsNtDdiVersionAvailable](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlisntddiversionavailable) routine instead of the **IoIsWdmVersionAvailable** routine.

Cross-platform drivers should use this routine to check the WDM version before performing any operations that vary by platform or are not supported in all versions of WDM.

The WDM_MAJORVERSION and WDM_MINORVERSION constants, which are defined in the Wdm.h header file, specify the WDM major and minor version numbers for the current version of Windows. The following lists the WDM version provided with each operating system.

| Operating system | WDM major version | WDM minor version |
|---|---|---|
| Windows 7 | 6 | 0x00 |
| Windows Server 2008 R2 | 6 | 0x00 |
| Windows Server 2008 | 6 | 0x00 |
| Windows Vista | 6 | 0x00 |
| Windows Server 2003 | 1 | 0x30 |
| Windows XP | 1 | 0x20 |
| Windows 2000 | 1 | 0x10 |
| Windows Me | 1 | 0x05 |
| Windows 98 | 1 | 0x00 |

Note that the minor version number is defined as a hexadecimal value.

Later versions of WDM support all the features available in earlier versions of WDM; that is, each version of WDM is a superset of the previous WDM version.

The following call returns **TRUE** on any of the listed operating systems, because all these systems support all the features of WDM 1.0:

```cpp
bVersion = IoIsWdmVersionAvailable(1,0);
```

The following example shows how a driver can dynamically detect the current operating system:

```cpp
if (IoIsWdmVersionAvailable(1, 0x10)) {
    //
    //If WDM 1.10 is supported, this is Windows 2000
    //or better.
    //
} else if (IoIsWdmVersionAvailable(1, 5)) {
    //
    //If WDM 1.05 is supported, this is Windows ME
    //or better.
    //
} else {
    //
    //WDM 1.0 is always supported, so this is Windows 98, 
    //Windows 98 SE, or better.
    //
}
```

As the example shows, calling **IoIsWdmVersionAvailable**(1, 5) returns **TRUE** on Windows Me, Windows 2000, and any succeeding operating systems, but **FALSE** on Windows 98 and Windows 98 SE.

## -see-also

[RtlIsNtDdiVersionAvailable](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlisntddiversionavailable)
