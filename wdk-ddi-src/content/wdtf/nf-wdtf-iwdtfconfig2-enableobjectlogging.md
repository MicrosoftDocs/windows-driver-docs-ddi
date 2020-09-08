---
UID: NF:wdtf.IWDTFCONFIG2.EnableObjectLogging
title: IWDTFCONFIG2::EnableObjectLogging (wdtf.h)
description: Enables object logging for all objects.
old-location: dtf\iwdtfconfig2_enableobjectlogging.htm
tech.root: dtf
ms.assetid: 7518aab0-8de5-4f45-b7d9-3cffdc07ea90
ms.date: 04/04/2018
keywords: ["IWDTFCONFIG2::EnableObjectLogging"]
ms.keywords: EnableObjectLogging, EnableObjectLogging method [Windows Device Testing Framework], EnableObjectLogging method [Windows Device Testing Framework],IWDTFCONFIG2 interface, IWDTFCONFIG2 interface [Windows Device Testing Framework],EnableObjectLogging method, IWDTFCONFIG2.EnableObjectLogging, IWDTFCONFIG2::EnableObjectLogging, Microsoft.WDTF.IWDTFCONFIG2.EnableObjectLogging, Microsoft::WDTF::IWDTFCONFIG2::EnableObjectLogging, dtf.iwdtfconfig2_enableobjectlogging, wdtf/IWDTFCONFIG2::EnableObjectLogging
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFCONFIG2::EnableObjectLogging
 - wdtf/IWDTFCONFIG2::EnableObjectLogging
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFCONFIG2.EnableObjectLogging
---

# IWDTFCONFIG2::EnableObjectLogging


## -description

Enables object logging for all objects.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

<b>WDTF</b> object logging defaults to disabled. If object logging is enabled, 
each <b>WDTF</b> object writes to the 
test scripts log.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtfconfig2">IWDTFCONFIG2</a>

