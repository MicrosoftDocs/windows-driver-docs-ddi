---
UID: NF:wiamdef.CWiaLogProc.CWiaLogProc
title: CWiaLogProc::CWiaLogProc (wiamdef.h)
description: The CWiaLogProc constructor is called when the function or method being logged is entered.
tech.root: image
ms.date: 04/19/2022
keywords: ["CWiaLogProc::CWiaLogProc"]
ms.keywords: CWiaLogProc, CWiaLogProc interface [Imaging Devices],CWiaLogProc method, CWiaLogProc method [Imaging Devices], CWiaLogProc method [Imaging Devices],CWiaLogProc interface, CWiaLogProc.CWiaLogProc, CWiaLogProc::CWiaLogProc, image.cwialogproc_cwialogproc, wiamdef/CWiaLogProc::CWiaLogProc
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
targetos: Windows
req.typenames: 
f1_keywords:
 - CWiaLogProc::CWiaLogProc
 - wiamdef/CWiaLogProc::CWiaLogProc
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wiamdef.h
api_name:
 - CWiaLogProc::CWiaLogProc
---

## -description

The **CWiaLogProc** constructor is called when the function or method being logged is entered.

## -parameters

### -param pIWiaLog

Defines the **IWiaLog** parameter **pIWiaLog*.

### -param ResourceID

Defines the **INT** parameter *ResourceID*.

### -param DetailLevel

Defines the **INT** parameter *DetailLevel*.

### -param pszMsg

Defines the **CHAR** parameter **pszMsg*.

## -see-also

[CWiaLogProcEx](./nf-wiamdef-cwialogprocex-cwialogprocex.md)