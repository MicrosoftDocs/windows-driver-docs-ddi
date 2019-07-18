---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlDeregisterUncProvider
title: FsRtlDeregisterUncProvider function (ntifs.h)
description: The FsRtlDeregisterUncProvider routine deregisters a redirector that was registered as a Universal Naming Convention (UNC) provider with the multiple UNC provider (MUP).
old-location: ifsk\fsrtlderegisteruncprovider.htm
tech.root: ifsk
ms.assetid: 3f53a22f-b5d6-4e3d-987d-989bd5840b2a
ms.date: 04/16/2018
ms.keywords: FsRtlDeregisterUncProvider, FsRtlDeregisterUncProvider routine [Installable File System Drivers], fsrtlref_d1eb1778-7643-44df-8f68-edc995b22246.xml, ifsk.fsrtlderegisteruncprovider, ntifs/FsRtlDeregisterUncProvider
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlDeregisterUncProvider"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlDeregisterUncProvider
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlDeregisterUncProvider function


## -description


The <b>FsRtlDeregisterUncProvider</b> routine deregisters a redirector that was registered as a Universal Naming Convention (UNC) provider with the multiple UNC provider (MUP).


## -parameters




### -param Handle [in]

MUP handle returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider">FsRtlRegisterUncProvider</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex">FsRtlRegisterUncProviderEx</a>.


## -returns



None




## -remarks



To register a UNC provider on Windows Server 2003, Windows XP, or Windows 2000, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider">FsRtlRegisterUncProvider</a>. 

To register a UNC provider on Windows Vista, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex">FsRtlRegisterUncProviderEx</a>.

For more information, see the following sections in the Design Guide:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/support-for-unc-naming-and-mup">Support for UNC Naming and MUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mup-changes-in-microsoft-windows-vista">MUP Changes in Microsoft Windows Vista</a>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider">FsRtlRegisterUncProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex">FsRtlRegisterUncProviderEx</a>
 

 

