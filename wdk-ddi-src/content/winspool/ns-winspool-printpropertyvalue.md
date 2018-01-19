---
UID: NS:winspool.PrintPropertyValue
title: PrintPropertyValue
author: windows-driver-content
description: .
old-location: print\printpropertyvalue.htm
old-project: print
ms.assetid: B442AE8E-A4CE-481A-A69C-496CBF3E4722
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: PrintPropertyValue, PrintPropertyValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winspool.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PrintPropertyValue
req.alt-loc: Winspool.h
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
req.typenames: PrintPropertyValue
req.product: Windows 10 or later.
---

# PrintPropertyValue structure



## -description




## -syntax

````
typedef struct {
  EPrintPropertyType ePropertyType;
  union {
    BYTE     propertyByte;
    PWSTR    propertyString;
    LONG     propertyInt32;
    LONGLONG propertyInt64;
    struct {
      DWORD  cbBuf;
      LPVOID pBuf;
    } propertyBlob;
  } value;
} PrintPropertyValue;
````


## -struct-fields

### -field ePropertyType


### -field value


### -field propertyBlob


### -field pBuf

TD

</dd>
</dl>
</dd>
</dl>

## -remarks
