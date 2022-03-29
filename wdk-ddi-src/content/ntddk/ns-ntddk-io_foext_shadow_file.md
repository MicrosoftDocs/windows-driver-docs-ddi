---
UID: NS:ntddk._IO_FOEXT_SHADOW_FILE
tech.root: kernel
title: IO_FOEXT_SHADOW_FILE (ntddk.h)
ms.date: 03/28/2022
targetos: Windows
description: This topic describes the IO_FOEXT_SHADOW_FILE structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: Ntddk.h 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: IO_FOEXT_SHADOW_FILE, *PIO_FOEXT_SHADOW_FILE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _IO_FOEXT_SHADOW_FILE
 - PIO_FOEXT_SHADOW_FILE
 - IO_FOEXT_SHADOW_FILE
f1_keywords:
 - _IO_FOEXT_SHADOW_FILE
 - ntddk/_IO_FOEXT_SHADOW_FILE
 - PIO_FOEXT_SHADOW_FILE
 - ntddk/PIO_FOEXT_SHADOW_FILE
 - IO_FOEXT_SHADOW_FILE
 - ntddk/IO_FOEXT_SHADOW_FILE
dev_langs:
 - c++
helpviewer_keywords:
 - _IO_FOEXT_SHADOW_FILE
---

## -description

This topic describes the **IO_FOEXT_SHADOW_FILE** structure.

## -struct-fields

### -field BackingFileObject

File object that backs this shadow file.

### -field BackingFltInstance

Filter instance on the target volume of the filter that manages this shadow file.

## -remarks

## -see-also
