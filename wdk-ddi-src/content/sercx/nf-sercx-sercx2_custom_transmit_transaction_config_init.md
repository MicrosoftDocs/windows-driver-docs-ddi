---
UID: NF:sercx.SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT
title: SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT function (sercx.h)
description: The SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT function initializes a SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG structure.
old-location: serports\sercx2_custom_transmit_transaction_config_init.htm
tech.root: serports
ms.assetid: 098A7BB0-B135-4E99-8BDA-1EF29A8C338F
ms.date: 04/23/2018
keywords: ["SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT function"]
ms.keywords: 2/SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT, SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT, SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT function [Serial Ports], serports.sercx2_custom_transmit_transaction_config_init
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Any level.
targetos: Windows
req.typenames: 
f1_keywords:
 - SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT
 - sercx/SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 2.0\Sercx.h
api_name:
 - SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT
---

# SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT function


## -description

The <b>SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT</b> function initializes a <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_custom_transmit_transaction_config">SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG</a> structure.

## -parameters

### -param Config 

[out]
A pointer to the <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_custom_transmit_transaction_config">SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG</a> structure that is to be initialized.

### -param EvtSerCx2CustomTransmitTransactionStart 

[in]
The value to load into the <b>EvtSerCx2CustomTransmitTransactionStart</b> member of the <b>SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG</b> structure. For more information, see the description of this member in <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_custom_transmit_transaction_config">SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG</a>.

## -remarks

Your serial controller driver must use this function to initialize a <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_custom_transmit_transaction_config">SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customtransmittransactioncreate">SerCx2CustomTransmitTransactionCreate</a> method.

<b>SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG</b>), and sets the <b>EvtSerCx2CustomTransmitTransactionStart</b> member to the value supplied as an input parameter to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT</b> call.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_custom_transmit_transaction_config">SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customtransmittransactioncreate">SerCx2CustomTransmitTransactionCreate</a>