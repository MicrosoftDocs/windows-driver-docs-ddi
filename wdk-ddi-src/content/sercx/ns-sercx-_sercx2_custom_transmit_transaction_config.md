---
UID: NS:sercx._SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG
title: _SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG (sercx.h)
description: The SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new custom-transmit-transaction object.
old-location: serports\sercx2_custom_transmit_transaction_config.htm
tech.root: serports
ms.assetid: 40655056-8E29-4A53-812D-5F006A95C827
ms.date: 04/23/2018
ms.keywords: "*PSERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG, 2/PSERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG, 2/SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG, PSERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG, PSERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG structure pointer [Serial Ports], SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG, SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG structure [Serial Ports], _SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG, serports.sercx2_custom_transmit_transaction_config"
ms.topic: struct
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
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
- SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG
product:
- Windows
targetos: Windows
req.typenames: SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG, *PSERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG
---

# _SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG structure


## -description


The <b>SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new custom-transmit-transaction object.


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/dn265259">SerCx2CustomTransmitTransactionCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field EvtSerCx2CustomTransmitTransactionInitialize

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/CFC577D6-747F-4752-8CB6-7410C21487B6">EvtSerCx2CustomTransmitTransactionInitialize</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2CustomTransmitTransactionStart

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/BFB2DBBE-9E00-4C1D-B336-2B9C48E98DD3">EvtSerCx2CustomTransmitTransactionStart</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2CustomTransmitTransactionCleanup

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/CEADF06B-FD60-4B4C-AB59-1ED6B1226204">EvtSerCx2CustomTransmitTransactionCleanup</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/dn265259">SerCx2CustomTransmitTransactionCreate</a> method accepts a pointer to a <b>SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2CustomTransmitTransactionInitialize</b>, call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265322">SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT</a> function to initialize this structure.




## -see-also




<a href="https://msdn.microsoft.com/CEADF06B-FD60-4B4C-AB59-1ED6B1226204">EvtSerCx2CustomTransmitTransactionCleanup</a>



<a href="https://msdn.microsoft.com/CFC577D6-747F-4752-8CB6-7410C21487B6">EvtSerCx2CustomTransmitTransactionInitialize</a>



<a href="https://msdn.microsoft.com/BFB2DBBE-9E00-4C1D-B336-2B9C48E98DD3">EvtSerCx2CustomTransmitTransactionStart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265322">SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265259">SerCx2CustomTransmitTransactionCreate</a>
 

 

