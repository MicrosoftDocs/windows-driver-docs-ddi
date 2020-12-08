---
UID: NF:ntddk.RtlIsStateSeparationEnabled
title: RtlIsStateSeparationEnabled function (ntddk.h)
description: Checks if the SKU for the current context supports multiple sessions.
old-location: kernel\rtlisstateseparationenabled.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlIsStateSeparationEnabled function"]
ms.keywords: RtlIsStateSeparationEnabled, RtlIsStateSeparationEnabled function [Kernel-Mode Driver Architecture], kernel.rtlisstateseparationenabled, ntddk/RtlIsStateSeparationEnabled
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlIsStateSeparationEnabled
 - ntddk/RtlIsStateSeparationEnabled
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlIsStateSeparationEnabled
---

# RtlIsStateSeparationEnabled function

## -description

Checks if the SKU for the current context supports multiple sessions.

## -returns

TRUE indicates state separation enabled and FALSE otherwise.
