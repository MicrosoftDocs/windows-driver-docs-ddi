---
UID: NF:spb.SPB_TRANSFER_LIST_INIT
title: SPB_TRANSFER_LIST_INIT function
author: windows-driver-content
description: The SPB_TRANSFER_LIST_INIT function initializes an SPB_TRANSFER_LIST structure.
old-location: spb\spb_transfer_list_init.htm
old-project: SPB
ms.assetid: 7FFFB495-7E6A-465C-AE93-B62957179531
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SPB.spb_transfer_list_init, SPB_TRANSFER_LIST_INIT, SPB_TRANSFER_LIST_INIT function [Buses], spb/SPB_TRANSFER_LIST_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spb.h
req.include-header: 
req.target-type: Desktop
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Spb.h
api_name:
-	SPB_TRANSFER_LIST_INIT
product: Windows
targetos: Windows
req.typenames: SPB_TRANSFER_DIRECTION, *PSPB_TRANSFER_DIRECTION
req.product: Windows 10 or later.
---

# SPB_TRANSFER_LIST_INIT function


## -description


The <b>SPB_TRANSFER_LIST_INIT</b> function initializes an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406221">SPB_TRANSFER_LIST</a> structure.


## -syntax


````
VOID SPB_TRANSFER_LIST_INIT(
  _Out_ SPB_TRANSFER_LIST *TransferList,
  _In_  ULONG             TransferCount
);
````


## -parameters




### -param TransferList [out]

A pointer to the <b>SPB_TRANSFER_LIST</b> structure that is to be initialized.


### -param TransferCount [in]

The number of entries in the transfer list. The function writes this value to the <b>TransferCount</b> member of the  <b>SPB_TRANSFER_LIST</b> structure.


## -returns



None.




## -remarks



To initialize the elements in the <b>SPB_TRANSFER_LIST</b> structure's <b>Transfers</b> array, use the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406214">SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh406213">SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/hh406202">SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST</a> function.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406221">SPB_TRANSFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406221">SPB_TRANSFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406213">SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED</a>



<<<<<<< HEAD
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406214">SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE</a>
=======
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406202">SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST</a>
>>>>>>> 7b6bd3b88106eb7b25c8489b98269eb870735b73



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_TRANSFER_LIST_INIT function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

