---
UID: NF:storport.StorPortWritePortUchar
title: StorPortWritePortUchar macro
author: windows-driver-content
description: The StorPortWritePortUchar routine writes a value to a specified register address.
old-location: storage\storportwriteportuchar.htm
old-project: storage
ms.assetid: 421bd075-e919-4389-af38-e0dd686f7c05
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: StorPortWritePortUchar routine [Storage Devices], storprt_602c6d78-179c-4eaa-8131-ec2be13b2050.xml, StorPortWritePortUchar, storage.storportwriteportuchar, storport/StorPortWritePortUchar
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
-	StorPortWritePortUchar
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortWritePortUchar macro


## -description


The <b>StorPortWritePortUchar</b> routine writes a value to a specified register address. 


## -syntax


````
STORPORT_API VOID StorPortWritePortUchar(
  _In_ PVOID  HwDeviceExtension,
  _In_ PUCHAR Port,
  _In_ UCHAR  Value
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



For more information, see <a href="..\srb\nf-srb-scsiportwriteportuchar.md">ScsiPortWritePortUchar</a>. For a buffered equivalent of this routine, see <a href="..\storport\nf-storport-storportwriteportbufferuchar.md">StorPortWritePortBufferUchar</a>. 




## -see-also

<a href="..\storport\nf-storport-storportwriteportbufferuchar.md">StorPortWritePortBufferUchar</a>



<a href="..\srb\nf-srb-scsiportwriteportuchar.md">ScsiPortWritePortUchar</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWritePortUchar routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

