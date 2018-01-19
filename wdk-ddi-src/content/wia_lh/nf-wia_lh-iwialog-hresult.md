---
UID: NF:wia_lh.IWiaLog.hResult
title: IWiaLog::hResult method
author: windows-driver-content
description: Note that the IWiaLog interface is obsolete for Microsoft Windows XP and later, and is no longer supported.
old-location: image\iwialog_hresult.htm
old-project: image
ms.assetid: 74d9b770-c2b6-483d-a6d7-070ac2a55133
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: IWiaLog, IWiaLog::hResult, hResult
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wia_lh.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me, Windows XP, and later. Obsoletefor Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IWiaLog.hResult
req.alt-loc: wia_lh.h
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
req.typenames: BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product: Windows 10 or later.
---

# IWiaLog::hResult method



## -description
Note that the <b>IWiaLog</b> interface is <b>obsolete </b>for Microsoft Windows XP and later, and is no longer supported. Instead, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540599">Diagnostic Log Macros</a>.

The <b>IWiaLog::hResult</b> method translates an HRESULT value into a string and writes the string to <i>Wiaservc.log</i>.



## -syntax

````
HRESULT hResult(
  [in] HRESULT hResult
);
````


## -parameters

### -param hResult [in]

Specifies the HRESULT value to translate into a string.


## -returns
If the method succeeds, it returns S_OK. If the method fails, it returns a standard COM error code.


## -remarks
