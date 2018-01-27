---
UID: NF:sercx.SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT
title: SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT function
author: windows-driver-content
description: The SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT function initializes a SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG structure.
old-location: serports\sercx2_custom_receive_transaction_config_init.htm
old-project: serports
ms.assetid: DB8A5E89-771C-45E8-8F90-708CDAD50BBF
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT, SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT function [Serial Ports], 2/SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT, serports.sercx2_custom_receive_transaction_config_init
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level.
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	2.0\Sercx.h
apiname: 
-	SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT function


## -description


The <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</b> function initializes a <a href="..\sercx\ns-sercx-_sercx2_custom_receive_transaction_config.md">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a> structure.


## -syntax


````
VOID SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT(
  _Out_    SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG    *Config,
  _In_     PFN_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START EvtSerCx2CustomReceiveTransactionStart,
  _In_opt_ PFN_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START EvtSerCx2CustomReceiveTransactionEnableNewDataNotification,
  _In_     PFN_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START EvtSerCx2CustomReceiveTransactionQueryProgress
);
````


## -parameters




### -param Config [out]

A pointer to the <a href="..\sercx\ns-sercx-_sercx2_custom_receive_transaction_config.md">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a> structure that is to be initialized.


### -param EvtSerCx2CustomReceiveTransactionStart [in]

The value to load into the <b>EvtSerCx2CustomReceiveTransactionStart</b> member of the <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_custom_receive_transaction_config.md">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a>.


### -param EvtSerCx2CustomReceiveTransactionEnableNewDataNotification [in, optional]

The value to load into the <b>EvtSerCx2CustomReceiveTransactionEnableNewDataNotification</b> member of the <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_custom_receive_transaction_config.md">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a>.


### -param EvtSerCx2CustomReceiveTransactionQueryProgress [in]

The value to load into the <b>EvtSerCx2CustomReceiveTransactionQueryProgress</b> member of the <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_custom_receive_transaction_config.md">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a>.


## -returns


None.



## -remarks


Your serial controller driver must use this function to initialize a <a href="..\sercx\ns-sercx-_sercx2_custom_receive_transaction_config.md">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a> method.

<b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b>), and sets three additional members of the structure to the values supplied as input parameters to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</b> call.



## -see-also

<a href="..\sercx\ns-sercx-_sercx2_custom_receive_transaction_config.md">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a>

<a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

