---
UID: NS:ntddk._PROCESS_READWRITEVM_LOGGING_INFORMATION
title: _PROCESS_READWRITEVM_LOGGING_INFORMATION (ntddk.h)
description: Stores options for read/write access for telemetry per process.
old-location: kernel\process_readwritevm_logging_information.htm
tech.root: kernel
ms.assetid: F1C769FD-D05F-4C23-A91E-FAEE8EA029EC
ms.date: 04/30/2018
ms.keywords: "*PPROCESS_READWRITEVM_LOGGING_INFORMATION, PPROCESS_READWRITEVM_LOGGING_INFORMATION, PPROCESS_READWRITEVM_LOGGING_INFORMATION union pointer [Kernel-Mode Driver Architecture], PROCESS_READWRITEVM_LOGGING_INFORMATION, PROCESS_READWRITEVM_LOGGING_INFORMATION union [Kernel-Mode Driver Architecture], _PROCESS_READWRITEVM_LOGGING_INFORMATION, kernel.process_readwritevm_logging_information, ntddk/PPROCESS_READWRITEVM_LOGGING_INFORMATION, ntddk/PROCESS_READWRITEVM_LOGGING_INFORMATION"
ms.topic: struct
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddk.h
api_name:
- PROCESS_READWRITEVM_LOGGING_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PROCESS_READWRITEVM_LOGGING_INFORMATION, *PPROCESS_READWRITEVM_LOGGING_INFORMATION
---

# _PROCESS_READWRITEVM_LOGGING_INFORMATION structure


## -description


Stores options for read/write access for  telemetry per process. 


## -struct-fields




### -field Flags

Reserved.


### -field EnableReadVmLogging

Enables or disables read access. Non-zero values enables telemetry, zero disables it.


### -field EnableWriteVmLogging

Enables or disables write access. Non-zero values enables telemetry, zero disables it.


### -field Unused

Do not use.

