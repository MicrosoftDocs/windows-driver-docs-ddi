---
UID: NS:sercx._SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG
title: _SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG (sercx.h)
description: The SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new custom-receive-transaction object.
old-location: serports\sercx2_custom_receive_transaction_config.htm
tech.root: serports
ms.assetid: 7D9E4F33-FCEE-4783-AE33-DCD3CB0286AE
ms.date: 04/23/2018
ms.keywords: "*PSERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG, 2/PSERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG, 2/SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG, PSERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG, PSERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG structure pointer [Serial Ports], SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG, SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG structure [Serial Ports], _SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG, serports.sercx2_custom_receive_transaction_config"
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
- SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG
product:
- Windows
targetos: Windows
req.typenames: SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG, *PSERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG
---

# _SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG structure


## -description


The <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new custom-receive-transaction object.


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field EvtSerCx2CustomReceiveTransactionInitialize

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/B3C23236-2A35-456A-B461-AEC688ACA5B7">EvtSerCx2CustomReceiveTransactionInitialize</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2CustomReceiveTransactionStart

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/F90250CC-EDBF-4DB7-B889-4BF6325FB0CD">EvtSerCx2CustomReceiveTransactionStart</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2CustomReceiveTransactionCleanup

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/72AF3D52-D109-42A7-9F25-14A3F5EDC94A">EvtSerCx2CustomReceiveTransactionCleanup</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2CustomReceiveTransactionEnableNewDataNotification

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/C3E446AB-17AA-4FD8-8245-16D95134B0E7">EvtSerCx2CustomReceiveTransactionEnableNewDataNotification</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2CustomReceiveTransactionQueryProgress

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/B0B08257-E867-4E22-949E-555AD44C2DDE">EvtSerCx2CustomReceiveTransactionQueryProgress</a> event callback function. This member must point to a valid function.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a> method accepts a pointer to a <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2CustomReceiveTransactionInitialize</b>, call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265316">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</a> function to initialize this structure.




## -see-also




<a href="https://msdn.microsoft.com/72AF3D52-D109-42A7-9F25-14A3F5EDC94A">EvtSerCx2CustomReceiveTransactionCleanup</a>



<a href="https://msdn.microsoft.com/C3E446AB-17AA-4FD8-8245-16D95134B0E7">EvtSerCx2CustomReceiveTransactionEnableNewDataNotification</a>



<a href="https://msdn.microsoft.com/B3C23236-2A35-456A-B461-AEC688ACA5B7">EvtSerCx2CustomReceiveTransactionInitialize</a>



<a href="https://msdn.microsoft.com/B0B08257-E867-4E22-949E-555AD44C2DDE">EvtSerCx2CustomReceiveTransactionQueryProgress</a>



<a href="https://msdn.microsoft.com/F90250CC-EDBF-4DB7-B889-4BF6325FB0CD">EvtSerCx2CustomReceiveTransactionStart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265316">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a>
 

 

