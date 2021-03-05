---
UID: NF:storport.StorPortSecureCopyMemory
tech.root: storage
title: StorPortSecureCopyMemory
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - storport.h
api_name:
 - StorPortSecureCopyMemory
f1_keywords:
 - StorPortSecureCopyMemory
 - storport/StorPortSecureCopyMemory
dev_langs:
 - c++
---

## -description

## -parameters

### -param Dest

[out] Pointer to the destination buffer to copy to.

### -param DestSizeInBytes

[in] Size of the buffer that **Dest** points to, in bytes.

### -param Src

[in] Pointer to the source buffer to copy from.
### -param Count

[in] Number of bytes to copy from **Src** to **Dest**.

## -returns

This function returns one of the following status codes.

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The specified number of bytes were copied. |
| STOR_STATUS_INVALID_PARAMETER | A parameter is invalid; for example, **Dest** is a null pointer. |
| STOR_STATUS_BUFFER_TOO_SMALL | The destination buffer size is smaller than number of bytes to copy.|

## -remarks

## -see-also
