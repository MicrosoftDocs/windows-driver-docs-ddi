---
UID: NF:wdm.ExIsSoftBoot
title: ExIsSoftBoot function (wdm.h)
description: Determines whether the system has gone through a soft restart.
old-location: kernel\exissoftboot.htm
tech.root: kernel
ms.assetid: ff67bc75-b424-4278-b979-f67d118232aa
ms.date: 04/30/2018
ms.keywords: ExIsSoftBoot, ExIsSoftBoot function [Kernel-Mode Driver Architecture], kernel.exissoftboot, wdm/ExIsSoftBoot
ms.topic: function
f1_keywords:
 - "wdm/ExIsSoftBoot"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExIsSoftBoot
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExIsSoftBoot function


## -description


Determines whether the system has gone through a soft restart.


## -returns



TRUE indicates a soft restart; FALSE otherwise.



