---
UID: NE:sercx._SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
title: "_SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS"
author: windows-driver-content
description: The SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS enumeration defines constants that indicate whether process is being made toward completing a custom-receive transaction.
old-location: serports\sercx2_custom_receive_transaction_progress.htm
old-project: serports
ms.assetid: B832554C-FB37-416F-9586-EFAB5A3633E5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, 2/SERCX2_CUSTOM_RECEIVE_BYTES_TRANSFERRED, 2/SERCX2_CUSTOM_RECEIVE_NO_PROGRESS, 2/SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, SERCX2_CUSTOM_RECEIVE_BYTES_TRANSFERRED, SERCX2_CUSTOM_RECEIVE_NO_PROGRESS, SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS enumeration [Serial Ports], _SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, serports.sercx2_custom_receive_transaction_progress"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sercx.h
req.include-header: 
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	2.0\Sercx.h
api_name:
-	SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
product: Windows
targetos: Windows
req.typenames: SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, *PSERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
req.product: Windows 10 or later.
---

# _SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS enumeration


## -description


The <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS</b> enumeration defines constants that indicate whether process is being made toward completing a custom-receive transaction.


## -enum-fields




### -field SerCx2CustomReceiveTransactionNoProgress


### -field SerCx2CustomReceiveTransactionBytesTransferred




#### - SERCX2_CUSTOM_RECEIVE_BYTES_TRANSFERRED

Progress is being made. This value indicates that one or more bytes of data have been transferred in the current custom-receive transaction since either the previous progress report or the start of the transaction, whichever is more recent.


#### - SERCX2_CUSTOM_RECEIVE_NO_PROGRESS

No progress is being made. This value indicates that no data bytes have been transferred in the current custom-receive transaction since either the previous progress report or the start of the transaction, whichever is more recent.


## -remarks



The constants in this enumeration are used by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265254">SerCx2CustomReceiveTransactionReportProgress</a> method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265254">SerCx2CustomReceiveTransactionReportProgress</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

