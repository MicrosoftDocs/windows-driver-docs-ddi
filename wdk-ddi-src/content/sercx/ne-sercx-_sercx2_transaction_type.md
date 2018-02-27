---
UID: NE:sercx._SERCX2_TRANSACTION_TYPE
title: "_SERCX2_TRANSACTION_TYPE"
author: windows-driver-content
description: The SERCX2_TRANSACTION_TYPE enumeration defines constants that indicate the type of data-transfer mechanism to use to perform an I/O transaction.
old-location: serports\sercx2_transaction_type.htm
old-project: serports
ms.assetid: 9F50CA34-DDEA-49E4-8149-B92D00476720
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SERCX2_TRANSACTION_TYPE, 2/SerCx2TransactionTypeCustom, 2/SerCx2TransactionTypeDefault, 2/SerCx2TransactionTypePio, 2/SerCx2TransactionTypeSystemDma, SERCX2_TRANSACTION_TYPE, SERCX2_TRANSACTION_TYPE enumeration [Serial Ports], SerCx2TransactionTypeCustom, SerCx2TransactionTypeDefault, SerCx2TransactionTypePio, SerCx2TransactionTypeSystemDma, _SERCX2_TRANSACTION_TYPE, serports.sercx2_transaction_type
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	2.0\Sercx.h
apiname:
-	SERCX2_TRANSACTION_TYPE
product: Windows
targetos: Windows
req.typenames: SERCX2_TRANSACTION_TYPE
req.product: Windows 10 or later.
---

# _SERCX2_TRANSACTION_TYPE enumeration


## -description


The <b>SERCX2_TRANSACTION_TYPE</b> enumeration defines constants that indicate the type of data-transfer mechanism to use to perform an I/O transaction.


## -syntax


````
typedef enum _SERCX2_TRANSACTION_TYPE { 
  SerCx2TransactionTypeDefault,
  SerCx2TransactionTypePio,
  SerCx2TransactionTypeSystemDma,
  SerCx2TransactionTypeCustom
} SERCX2_TRANSACTION_TYPE;
````


## -enum-fields




### -field SerCx2TransactionTypeDefault

Let SerCx2 decide what type of data transfer to use for the I/O transaction.


### -field SerCx2TransactionTypePio

Use programmed I/O (PIO) to perform the I/O transaction.


### -field SerCx2TransactionTypeSystemDma

Use system DMA to perform the I/O transaction.


### -field SerCx2TransactionTypeCustom

Use the custom data-transfer mechanism to perform the I/O transaction.


## -remarks



The <a href="..\sercx\nc-sercx-evt_sercx2_select_next_receive_transaction_type.md">EvtSerCx2SelectNextReceiveTransactionType</a> and <a href="..\sercx\nc-sercx-evt_sercx2_select_next_transmit_transaction_type.md">EvtSerCx2SelectNextTransmitTransactionType</a> event callback functions return <b>SERCX2_TRANSACTION_TYPE</b> enumeration values.




## -see-also

<a href="..\sercx\nc-sercx-evt_sercx2_select_next_transmit_transaction_type.md">EvtSerCx2SelectNextTransmitTransactionType</a>



<a href="..\sercx\nc-sercx-evt_sercx2_select_next_receive_transaction_type.md">EvtSerCx2SelectNextReceiveTransactionType</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_TRANSACTION_TYPE enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

