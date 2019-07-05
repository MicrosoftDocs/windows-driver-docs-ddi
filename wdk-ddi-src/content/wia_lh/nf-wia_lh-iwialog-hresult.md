---
UID: NF:wia_lh.IWiaLog.hResult
title: IWiaLog::hResult (wia_lh.h)
description: Note that the IWiaLog interface is obsolete and is no longer supported.
old-location: image\iwialog_hresult.htm
tech.root: image
ms.assetid: 74d9b770-c2b6-483d-a6d7-070ac2a55133
ms.date: 05/03/2018
ms.keywords: IWiaLog interface [Imaging Devices],hResult method, IWiaLog.hResult, IWiaLog::hResult, IWiaLog_e581a82d-60c1-45e3-9d5a-fcac2b4d9c9c.xml, hResult, hResult method [Imaging Devices], hResult method [Imaging Devices],IWiaLog interface, image.iwialog_hresult, wia_lh/IWiaLog::hResult
ms.topic: method
req.header: wia_lh.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Obsolete and is no longer supported. Instead, use the Diagnostic Log Macros.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wia_lh.h
api_name:
- IWiaLog.hResult
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaLog::hResult

## -description

Note that the **IWiaLog** interface is obsolete and is no longer supported. Instead, use the [Diagnostic Log Macros](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_image/index).

The **IWiaLog::hResult** method translates an HRESULT value into a string and writes the string to *Wiaservc.log*.

## -parameters

### -param hResult [in]

Specifies the HRESULT value to translate into a string.

## -returns

If the method succeeds, it returns S_OK. If the method fails, it returns a standard COM error code.
