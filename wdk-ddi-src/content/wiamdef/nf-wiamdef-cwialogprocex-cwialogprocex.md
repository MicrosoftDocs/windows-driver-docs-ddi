---
UID: NF:wiamdef.CWiaLogProcEx.CWiaLogProcEx
title: CWiaLogProcEx::CWiaLogProcEx (wiamdef.h)
description: The CWiaLogProcEx constructor is called when the function or method being logged is entered.
old-location: image\cwialogprocex_cwialogprocex.htm
tech.root: image
ms.assetid: D4004501-2DA5-416C-A29B-C0084CF34DC9
ms.date: 05/03/2018
keywords: ["CWiaLogProcEx::CWiaLogProcEx"]
ms.keywords: CWiaLogProcEx, CWiaLogProcEx interface [Imaging Devices],CWiaLogProcEx method, CWiaLogProcEx method [Imaging Devices], CWiaLogProcEx method [Imaging Devices],CWiaLogProcEx interface, CWiaLogProcEx.CWiaLogProcEx, CWiaLogProcEx::CWiaLogProcEx, image.cwialogprocex_cwialogprocex, wiamdef/CWiaLogProcEx::CWiaLogProcEx
f1_keywords:
 - "wiamdef/CWiaLogProcEx.CWiaLogProcEx"
 - "CWiaLogProcEx.CWiaLogProcEx"
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- Wiamdef.h
api_name:
- CWiaLogProcEx.CWiaLogProcEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# CWiaLogProcEx::CWiaLogProcEx

## -description

The [CWiaLogProcEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-cwialogproc-~cwialogproc) constructor is called when the function or method being logged is entered.

## -parameters

### -param pIWiaLog

### -param ResourceID

Defines the **INT** parameter *ResourceID*.

### -param DetailLevel

Defines the **INT** parameter *DetailLevel*.

### -param pszMsg

### -param lMethodId

#### - *pIWiaLogEx

Defines the **IWiaLogEx** parameter **pIWiaLog*.

#### - *pszMsg

Defines the **CHAR** parameter **pszMsg*.

#### - lMethodId = 0

Defines the **LONG** parameter *lMethodId*.

## -see-also

[CWiaLogProcEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-cwialogprocex-cwialogprocex)
