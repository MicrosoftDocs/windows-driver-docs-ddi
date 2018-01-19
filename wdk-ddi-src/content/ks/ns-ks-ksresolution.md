---
UID: NS:ks.KSRESOLUTION
title: KSRESOLUTION
author: windows-driver-content
description: The KSRESOLUTION structure specifies granularity and error of a kernel streaming clock.
old-location: stream\ksresolution.htm
old-project: stream
ms.assetid: fbd6222c-6d54-4e2a-aa5b-8051f0838886
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSRESOLUTION, KSRESOLUTION, *PKSRESOLUTION
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
req.alt-api: KSRESOLUTION
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
req.typenames: KSRESOLUTION, *PKSRESOLUTION
---

# KSRESOLUTION structure



## -description
The KSRESOLUTION structure specifies granularity and error of a kernel streaming clock.



## -syntax

````
typedef struct {
  LONGLONG Granularity;
  LONGLONG Error;
} KSRESOLUTION, *PKSRESOLUTION;
````


## -struct-fields

### -field Granularity

Specifies the increment granularity of the clock in 100-nanosecond units, where 1 is the best.


### -field Error

Specifies the +/- notification error of the clock in 100-nanosecond units, where 0 is the best, meaning the event notification granularity is as good as the increment granularity.


## -remarks
Vendors can supply a structure of type KSRESOLUTION in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a> property request.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSRESOLUTION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

