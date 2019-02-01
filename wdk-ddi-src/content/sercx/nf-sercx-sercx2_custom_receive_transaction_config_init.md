---
UID: NF:sercx.SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT
title: SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT function (sercx.h)
description: The SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT function initializes a SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG structure.
old-location: serports\sercx2_custom_receive_transaction_config_init.htm
tech.root: serports
ms.assetid: DB8A5E89-771C-45E8-8F90-708CDAD50BBF
ms.date: 04/23/2018
ms.keywords: 2/SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT, SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT, SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT function [Serial Ports], serports.sercx2_custom_receive_transaction_config_init
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	2.0\Sercx.h
api_name:
-	SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT function


## -description


The <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265315">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265315">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a> structure that is to be initialized.


### -param EvtSerCx2CustomReceiveTransactionStart [in]

The value to load into the <b>EvtSerCx2CustomReceiveTransactionStart</b> member of the <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b> structure. For more information, see the description of this member in <a href="https://msdn.microsoft.com/library/windows/hardware/dn265315">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a>.


### -param EvtSerCx2CustomReceiveTransactionEnableNewDataNotification [in, optional]

The value to load into the <b>EvtSerCx2CustomReceiveTransactionEnableNewDataNotification</b> member of the <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b> structure. For more information, see the description of this member in <a href="https://msdn.microsoft.com/library/windows/hardware/dn265315">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a>.


### -param EvtSerCx2CustomReceiveTransactionQueryProgress [in]

The value to load into the <b>EvtSerCx2CustomReceiveTransactionQueryProgress</b> member of the <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b> structure. For more information, see the description of this member in <a href="https://msdn.microsoft.com/library/windows/hardware/dn265315">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a>.


## -returns



None.




## -remarks



Your serial controller driver must use this function to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265315">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a> method.

<b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b>), and sets three additional members of the structure to the values supplied as input parameters to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</b> call.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265315">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a>
 

 

