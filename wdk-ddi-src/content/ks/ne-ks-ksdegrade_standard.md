---
UID: NE:ks.KSDEGRADE_STANDARD
title: KSDEGRADE_STANDARD
author: windows-driver-content
description: The KSDEGRADE_STANDARD enumeration lists different types of degradation.
old-location: stream\ksdegrade_standard.htm
old-project: stream
ms.assetid: 5790ce0e-13f8-4700-8b25-a5375dd83758
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KSDEGRADE_STANDARD, ks/KSDEGRADE_STANDARD_SAMPLE, stream.ksdegrade_standard, ks/KSDEGRADE_STANDARD_SKIP, ks-struct_933ec08b-6ad6-47dc-8092-357d6bbe1c72.xml, KSDEGRADE_STANDARD_SAMPLE, ks/KSDEGRADE_STANDARD_COMPUTATION, KSDEGRADE_STANDARD_COMPUTATION, ks/KSDEGRADE_STANDARD_QUALITY, KSDEGRADE_STANDARD, KSDEGRADE_STANDARD_QUALITY, KSDEGRADE_STANDARD enumeration [Streaming Media Devices], KSDEGRADE_STANDARD_SKIP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: Ks.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSDEGRADE_STANDARD
product: Windows
targetos: Windows
req.typenames: KSDEGRADE_STANDARD
---

# KSDEGRADE_STANDARD enumeration


## -description


The KSDEGRADE_STANDARD enumeration lists different types of degradation.


## -syntax


````
typedef enum  { 
  KSDEGRADE_STANDARD_SAMPLE       = 0,
  KSDEGRADE_STANDARD_QUALITY      = 1,
  KSDEGRADE_STANDARD_COMPUTATION  = 2,
  KSDEGRADE_STANDARD_SKIP         = 3
} KSDEGRADE_STANDARD;
````


## -enum-fields




#### - KSDEGRADE_STANDARD_SAMPLE

Specifies sample degradation.


#### - KSDEGRADE_STANDARD_QUALITY

Specifies quality degradation.


#### - KSDEGRADE_STANDARD_COMPUTATION

Specifies computation degradation.


#### - KSDEGRADE_STANDARD_SKIP

Requests to skip ahead a specified delta in the data stream.


## -remarks


For more information, see <a href="https://msdn.microsoft.com/359e6e12-903f-4037-8f35-b090ce41f770">Quality Management</a>.



## -see-also

<a href="..\ks\ns-ks-ksidentifier.md">KSDEGRADE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSDEGRADE_STANDARD enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

