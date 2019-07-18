---
UID: NF:wia_lh.IWiaLog.InitializeLog
title: IWiaLog::InitializeLog (wia_lh.h)
description: Note that the IWiaLog interface is obsolete and is no longer supported. Instead, use the Diagnostic Log Macros.The IWiaLog::InitializeLog method initializes the lWiaLog interface.
old-location: image\iwialog_initializelog.htm
tech.root: image
ms.assetid: ef637329-a291-445b-8ac7-6e55d5d7931e
ms.date: 05/03/2018
ms.keywords: IWiaLog interface [Imaging Devices],InitializeLog method, IWiaLog.InitializeLog, IWiaLog::InitializeLog, IWiaLog_17cc24cb-d8dd-4f7c-b5d4-6720621b6534.xml, InitializeLog, InitializeLog method [Imaging Devices], InitializeLog method [Imaging Devices],IWiaLog interface, image.iwialog_initializelog, wia_lh/IWiaLog::InitializeLog
ms.topic: method
f1_keywords:
 - "wia_lh/IWiaLog.InitializeLog"
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
- IWiaLog.InitializeLog
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaLog::InitializeLog

## -description

Note that the **IWiaLog** interface is obsolete and is no longer supported. Instead, use the [Diagnostic Log Macros](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_image/index).

The **IWiaLog::InitializeLog** method initializes the **lWiaLog** interface.

## -parameters

### -param hInstance [in]

Specifies the module handle. This parameter indicates which module is calling the method.

## -returns

If the method succeeds, it returns S_OK. If the method fails, it returns a standard COM error code.

## -remarks

The minidriver should call [CoCreateInstance](https://docs.microsoft.com/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) or [CoCreateInstanceEx](https://docs.microsoft.com/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstanceex) to obtain the [IWiaLog](https://docs.microsoft.com/windows/win32/api/wia_xp/nn-wia_xp-iwialog) interface.
