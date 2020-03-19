---
UID: NE:sercx._SERCX2_TRANSACTION_TYPE
title: _SERCX2_TRANSACTION_TYPE (sercx.h)
description: The SERCX2_TRANSACTION_TYPE enumeration defines constants that indicate the type of data-transfer mechanism to use to perform an I/O transaction.
old-location: serports\sercx2_transaction_type.htm
tech.root: serports
ms.assetid: 9F50CA34-DDEA-49E4-8149-B92D00476720
ms.date: 04/23/2018
keywords: ["_SERCX2_TRANSACTION_TYPE enumeration"]
ms.keywords: 2/SERCX2_TRANSACTION_TYPE, 2/SerCx2TransactionTypeCustom, 2/SerCx2TransactionTypeDefault, 2/SerCx2TransactionTypePio, 2/SerCx2TransactionTypeSystemDma, SERCX2_TRANSACTION_TYPE, SERCX2_TRANSACTION_TYPE enumeration [Serial Ports], SerCx2TransactionTypeCustom, SerCx2TransactionTypeDefault, SerCx2TransactionTypePio, SerCx2TransactionTypeSystemDma, _SERCX2_TRANSACTION_TYPE, serports.sercx2_transaction_type
f1_keywords:
 - "sercx/SERCX2_TRANSACTION_TYPE"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 2.0\Sercx.h
api_name:
- SERCX2_TRANSACTION_TYPE
product:
- Windows
targetos: Windows
req.typenames: SERCX2_TRANSACTION_TYPE
---

# _SERCX2_TRANSACTION_TYPE enumeration


## -description


The <b>SERCX2_TRANSACTION_TYPE</b> enumeration defines constants that indicate the type of data-transfer mechanism to use to perform an I/O transaction.


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



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_select_next_receive_transaction_type">EvtSerCx2SelectNextReceiveTransactionType</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_select_next_transmit_transaction_type">EvtSerCx2SelectNextTransmitTransactionType</a> event callback functions return <b>SERCX2_TRANSACTION_TYPE</b> enumeration values.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_select_next_receive_transaction_type">EvtSerCx2SelectNextReceiveTransactionType</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_select_next_transmit_transaction_type">EvtSerCx2SelectNextTransmitTransactionType</a>
 

 

