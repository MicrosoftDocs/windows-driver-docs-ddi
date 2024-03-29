---
UID: NF:ntifs.FsRtlDeregisterUncProvider
title: FsRtlDeregisterUncProvider function (ntifs.h)
description: The FsRtlDeregisterUncProvider routine deregisters a redirector that was registered as a Universal Naming Convention (UNC) provider with the multiple UNC provider (MUP).
old-location: ifsk\fsrtlderegisteruncprovider.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlDeregisterUncProvider function"]
ms.keywords: FsRtlDeregisterUncProvider, FsRtlDeregisterUncProvider routine [Installable File System Drivers], fsrtlref_d1eb1778-7643-44df-8f68-edc995b22246.xml, ifsk.fsrtlderegisteruncprovider, ntifs/FsRtlDeregisterUncProvider
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlDeregisterUncProvider
 - ntifs/FsRtlDeregisterUncProvider
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlDeregisterUncProvider
---

# FsRtlDeregisterUncProvider function


## -description

The <b>FsRtlDeregisterUncProvider</b> routine deregisters a redirector that was registered as a Universal Naming Convention (UNC) provider with the multiple UNC provider (MUP).

## -parameters

### -param Handle [in]


MUP handle returned by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider">FsRtlRegisterUncProvider</a> or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex">FsRtlRegisterUncProviderEx</a>.

## -remarks

To register a UNC provider on Windows Server 2003, Windows XP, or Windows 2000, use <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider">FsRtlRegisterUncProvider</a>. 

To register a UNC provider on Windows Vista, use <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex">FsRtlRegisterUncProviderEx</a>.

For more information, see the following sections in the Design Guide:


<a href="/windows-hardware/drivers/ifs/support-for-unc-naming-and-mup">Support for UNC Naming and MUP</a>



<a href="/windows-hardware/drivers/ifs/mup-changes-in-microsoft-windows-vista">MUP Changes in Microsoft Windows Vista</a>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider">FsRtlRegisterUncProvider</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex">FsRtlRegisterUncProviderEx</a>
