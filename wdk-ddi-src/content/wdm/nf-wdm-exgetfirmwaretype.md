---
UID: NF:wdm.ExGetFirmwareType
title: ExGetFirmwareType function (wdm.h)
description: Returns the system firmware type.
old-location: kernel\exgetfirmwaretype.htm
tech.root: kernel
ms.date: 10/28/2021
keywords: ["ExGetFirmwareType function"]
ms.keywords: ExGetFirmwareType, ExGetFirmwareType function [Kernel-Mode Driver Architecture], kernel.exgetfirmwaretype, wdm/ExGetFirmwareType
req.header: wdm.h
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
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExGetFirmwareType
 - wdm/ExGetFirmwareType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExGetFirmwareType
---

# ExGetFirmwareType function


## -description

Returns the system firmware type.


## -returns

Returns a <a href="/windows/win32/api/winnt/ne-winnt-firmware_type">FIRMWARE_TYPE</a>-type value that indicates the type of firmware.
