---
UID: NF:wiamdef.WIAS_LHRESULT
title: WIAS_LHRESULT macro (wiamdef.h)
description: The WIAS_LHRESULT macro is obsolete. It is recommended that the WIAS_HRESULT macro be used instead. The WIAS_LHRESULT macro translates an HRESULT value into a string and writes the string to the diagnostic log file.
old-location: image\wias_lhresult.htm
tech.root: image
ms.assetid: dcc02735-632f-4b86-ac4f-833c8dcba1c5
ms.date: 05/03/2018
keywords: ["WIAS_LHRESULT macro"]
ms.keywords: IWiaLog_f9693b87-6464-423a-9b50-f715f3b35f36.xml, WIAS_LHRESULT, WIAS_LHRESULT macro [Imaging Devices], image.wias_lhresult, wiamdef/WIAS_LHRESULT
req.header: wiamdef.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Obsolete, use WIAS_HRESULT instead.
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
 - WIAS_LHRESULT
 - wiamdef/WIAS_LHRESULT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiamdef.h
api_name:
 - WIAS_LHRESULT
---

# WIAS_LHRESULT macro (wiamdef.h)


## -description

The WIAS_LHRESULT macro is obsolete. It is recommended that the [WIAS_HRESULT](./nf-wiamdef-wias_hresult.md) macro be used instead. The WIAS_LHRESULT macro translates an HRESULT value into a string and writes the string to the diagnostic log file.

## -parameters

### -param pILog

### -param hr

Specifies the HRESULT value to be translated into a string.

- **pIWiaLog** - Pointer to an [IWiaLog Interface](../wia_lh/nn-wia_lh-iwialog.md).

## -remarks

The following is an example of how the macro can be used:

```cpp
hr = wiasFreePropContext(*pContext);
if (hr != S_OK)
   WIAS_LHRESULT(g_pIWiaLog, hr);
```

The WIAS_LHRESULT macro is obsolete. It is recommended that the [WIAS_HRESULT](./nf-wiamdef-wias_hresult.md) macro be used instead.

## -see-also

[WIAS_HRESULT](./nf-wiamdef-wias_hresult.md)

[WIAS_LERROR](./nf-wiamdef-wias_lerror.md)

[WIAS_LTRACE](./nf-wiamdef-wias_ltrace.md)

[WIAS_LWARNING](./nf-wiamdef-wias_lwarning.md)