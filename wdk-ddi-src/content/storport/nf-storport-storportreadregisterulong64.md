---
UID: NF:storport.StorPortReadRegisterUlong64
title: StorPortReadRegisterUlong64 macro
author: windows-driver-content
description: The StorPortReadRegisterUlong64 routine reads a 64-bit value from a specified 64-bit register address.
old-location: storage\storportreadregisterulong64.htm
old-project: storage
ms.assetid: 73A9E645-0B71-429F-9033-032BB83E60E4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: StorPortReadRegisterUlong64, StorPortReadRegisterUlong64 routine [Storage Devices], storage.storportreadregisterulong64, storport/StorPortReadRegisterUlong64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: storport.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortReadRegisterUlong64
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortReadRegisterUlong64 macro


## -description


The <b>StorPortReadRegisterUlong64</b> routine reads a 64-bit value from a specified 64-bit register address.


## -syntax


````
 VOID StorPortReadRegisterUlong64(
  _In_ PULONG64  Register
);
````


## -parameters




### -param h

TBD


### -param r

TBD






#### - Register [in]

Pointer to the register where the data is to be read. 


## -remarks



The <b>StorPortReadRegisterUlong64</b> routine is only available on the 64-bit version of Windows.




## -see-also

<a href="..\storport\nf-storport-storportwriteregisterulong64.md">StorPortWriteRegisterUlong64</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadRegisterUlong64 routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

