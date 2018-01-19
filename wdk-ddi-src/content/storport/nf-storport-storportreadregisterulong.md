---
UID: NF:storport.StorPortReadRegisterUlong
title: StorPortReadRegisterUlong function
author: windows-driver-content
description: The StorPortReadRegisterUlong routine reads a value from a specified register address.
old-location: storage\storportreadregisterulong.htm
old-project: storage
ms.assetid: 308e6401-9726-4333-bde8-1aec9558c5fb
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortReadRegisterUlong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortReadRegisterUlong
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortReadRegisterUlong function



## -description
The <b>StorPortReadRegisterUlong</b> routine reads a value from a specified register address. 



## -syntax

````
STORPORT_API ULONG StorPortReadRegisterUlong(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Register
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the hardware device extension.


### -param Register [in]

Pointer to the register where the data is to be read. 


## -returns
<b>StorPortReadRegisterUlong</b> returns an unsigned character of data read from the indicated register address. 


## -remarks
For more information, see <a href="..\srb\nf-srb-scsiportreadregisterulong.md">ScsiPortReadRegisterUlong</a>. For a buffered version of this routine, see <a href="..\storport\nf-storport-storportreadregisterbufferulong.md">StorPortReadRegisterBufferUlong</a>.


## -see-also
<dl>
<dt>
<a href="..\srb\nf-srb-scsiportreadregisterulong.md">ScsiPortReadRegisterUlong</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportreadregisterbufferulong.md">StorPortReadRegisterBufferUlong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadRegisterUlong routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

