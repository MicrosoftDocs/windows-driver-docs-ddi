---
UID: NF:wdtf.IWDTFCONFIG2.DisableObjectLogging
title: IWDTFCONFIG2::DisableObjectLogging (wdtf.h)
description: Disables object logging for all objects.
old-location: dtf\iwdtfconfig2_disableobjectlogging.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFCONFIG2::DisableObjectLogging"]
ms.keywords: DisableObjectLogging, DisableObjectLogging method [Windows Device Testing Framework], DisableObjectLogging method [Windows Device Testing Framework],IWDTFCONFIG2 interface, IWDTFCONFIG2 interface [Windows Device Testing Framework],DisableObjectLogging method, IWDTFCONFIG2.DisableObjectLogging, IWDTFCONFIG2::DisableObjectLogging, Microsoft.WDTF.IWDTFCONFIG2.DisableObjectLogging, Microsoft::WDTF::IWDTFCONFIG2::DisableObjectLogging, dtf.iwdtfconfig2_disableobjectlogging, wdtf/IWDTFCONFIG2::DisableObjectLogging
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
 - IWDTFCONFIG2::DisableObjectLogging
 - wdtf/IWDTFCONFIG2::DisableObjectLogging
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFCONFIG2::DisableObjectLogging
---

# IWDTFCONFIG2::DisableObjectLogging


## -description

Disables object logging for all objects.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

<b>WDTF</b> logging defaults to disabled. If logging is enabled, 
each <b>WDTF</b> object writes to the 
test scripts log.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtfconfig2">IWDTFCONFIG2</a>

