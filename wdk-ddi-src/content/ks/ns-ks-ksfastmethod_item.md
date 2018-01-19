---
UID: NS:ks.KSFASTMETHOD_ITEM
title: KSFASTMETHOD_ITEM
author: windows-driver-content
description: Drivers provide a structure of type KSFASTMETHOD_ITEM to support fast I/O dispatching.
old-location: stream\ksfastmethod_item.htm
old-project: stream
ms.assetid: 71e59c73-d77d-4b10-9d13-f5d21338eb94
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSFASTMETHOD_ITEM, KSFASTMETHOD_ITEM, *PKSFASTMETHOD_ITEM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSFASTMETHOD_ITEM
req.alt-loc: ks.h
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
req.typenames: KSFASTMETHOD_ITEM, *PKSFASTMETHOD_ITEM
---

# KSFASTMETHOD_ITEM structure



## -description
Drivers provide a structure of type KSFASTMETHOD_ITEM to support fast I/O dispatching.



## -syntax

````
typedef struct {
  ULONG MethodId;
  union {
    PFNKSFASTHANDLER MethodHandler;
    BOOLEAN          MethodSupported;
  };
} KSFASTMETHOD_ITEM, *PKSFASTMETHOD_ITEM;
````


## -struct-fields

### -field MethodId

Contains the identifier of the method and the flags describing the type of method.


### -field MethodHandler

Points to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567173">KStrFastHandler</a> routine for this method.


### -field MethodSupported

Set to <b>TRUE</b> if the method is supported, otherwise set to <b>FALSE</b>.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567173">KStrFastHandler</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSFASTMETHOD_ITEM structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

