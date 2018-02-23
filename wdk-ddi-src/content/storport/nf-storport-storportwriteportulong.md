---
UID: NF:storport.StorPortWritePortUlong
title: StorPortWritePortUlong macro
author: windows-driver-content
description: The StorPortWritePortUlong routine writes a value to a specified register address.
old-location: storage\storportwriteportulong.htm
old-project: storage
ms.assetid: 7c6d61c6-40e5-46fd-8c18-1f9d89c58515
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storport/StorPortWritePortUlong, storage.storportwriteportulong, StorPortWritePortUlong routine [Storage Devices], StorPortWritePortUlong, storprt_4f568f62-adb7-4176-9229-e2af5d4453cb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortWritePortUlong
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortWritePortUlong macro


## -description


The <b>StorPortWritePortUlong</b> routine writes a value to a specified register address. 


## -syntax


````
STORPORT_API VOID StorPortWritePortUlong(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Port,
  _In_ ULONG  Value
);
````


## -parameters




### -param h

TBD


### -param p

TBD


### -param v

TBD






#### - HwDeviceExtension [in]

Pointer to the hardware device extension.


#### - Port [in]

Contains the address of the port to be written to. 


#### - Value [in]

Contains the value to be written. 


## -remarks



For more information, see <a href="..\srb\nf-srb-scsiportwriteportulong.md">ScsiPortWritePortUlong</a>. For a buffered equivalent of this routine, see <a href="..\storport\nf-storport-storportwriteportbufferulong.md">StorPortWritePortBufferUlong</a>. 




## -see-also

<a href="..\storport\nf-storport-storportwriteportbufferulong.md">StorPortWritePortBufferUlong</a>



<a href="..\srb\nf-srb-scsiportwriteportulong.md">ScsiPortWritePortUlong</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWritePortUlong routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

