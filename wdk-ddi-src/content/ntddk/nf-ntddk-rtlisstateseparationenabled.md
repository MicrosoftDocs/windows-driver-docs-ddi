---
UID: NF:ntddk.RtlIsStateSeparationEnabled
title: RtlIsStateSeparationEnabled function (ntddk.h)
description: Checks if the SKU for the current context supports multiple sessions.
old-location: kernel\rtlisstateseparationenabled.htm
tech.root: kernel
ms.assetid: 7c28a82c-e039-4045-94cd-b47a45d15e28
ms.date: 04/30/2018
ms.keywords: RtlIsStateSeparationEnabled, RtlIsStateSeparationEnabled function [Kernel-Mode Driver Architecture], kernel.rtlisstateseparationenabled, ntddk/RtlIsStateSeparationEnabled
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.dll: NtosKrnl.exe (kernel mode)
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlIsStateSeparationEnabled
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIsStateSeparationEnabled function


## -description



			
            Checks if the SKU for the current context supports multiple
    sessions.



## -parameters






## -returns



 TRUE indicates state separation enabled;

    FALSE otherwise.



