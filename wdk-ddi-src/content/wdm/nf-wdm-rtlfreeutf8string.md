---
UID: NF:wdm.RtlFreeUTF8String
title: RtlFreeUTF8String function
author: windows-driver-content
description: TBD
tech.root: kernel
ms.assetid: 982c52a4-2b20-49d8-8984-443aaea3f438
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: function
ms.keywords: RtlFreeUTF8String
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- 
api_location: 
- 
api_name: 
- RtlFreeUTF8String
product: 
- Windows
targetos: Windows

---

# RtlFreeUTF8String function


## -description

The <b>RtlFreeUTF8String</b> routine releases storage that was allocated by <b>RtlUnicodeStringToUTF8String</b>.

## -parameters

### -param utf8String

Pointer to the UTF8 string buffer previously allocated by <b>RtlUnicodeStringToUTF8String</b>. 


## -remarks

This routine only releases the UTF8 string buffer passed to it; it does not release the Unicode string buffer passed to <b>RtlUnicodeStringToUTF8String</b>. 


## -see-also

[**RtlUnicodeStringToUTF8String**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlunicodestringtoutf8string)

