---
UID: NF:sercx.SERCX2_CUSTOM_RECEIVE_CONFIG_INIT
title: SERCX2_CUSTOM_RECEIVE_CONFIG_INIT function
author: windows-driver-content
description: The SERCX2_CUSTOM_RECEIVE_CONFIG_INIT function initializes a SERCX2_CUSTOM_RECEIVE_CONFIG structure.
old-location: serports\sercx2_custom_receive_config_init.htm
old-project: serports
ms.assetid: 35C7AE64-C778-443E-9CF7-7868048DA01F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SERCX2_CUSTOM_RECEIVE_CONFIG_INIT, SERCX2_CUSTOM_RECEIVE_CONFIG_INIT, SERCX2_CUSTOM_RECEIVE_CONFIG_INIT function [Serial Ports], serports.sercx2_custom_receive_config_init
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
-	SERCX2_CUSTOM_RECEIVE_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SERCX2_CUSTOM_RECEIVE_CONFIG_INIT function


## -description


The <b>SERCX2_CUSTOM_RECEIVE_CONFIG_INIT</b> function initializes a <a href="..\sercx\ns-sercx-_sercx2_custom_receive_config.md">SERCX2_CUSTOM_RECEIVE_CONFIG</a> structure.


## -syntax


````
VOID SERCX2_CUSTOM_RECEIVE_CONFIG_INIT(
  _Out_ SERCX2_CUSTOM_RECEIVE_CONFIG *Config
);
````


## -parameters




### -param Config [out]

A pointer to the <a href="..\sercx\ns-sercx-_sercx2_custom_receive_config.md">SERCX2_CUSTOM_RECEIVE_CONFIG</a> structure that is to be initialized.


## -returns



None.




## -remarks



Your serial controller driver must use this function to initialize a <a href="..\sercx\ns-sercx-_sercx2_custom_receive_config.md">SERCX2_CUSTOM_RECEIVE_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="..\sercx\nf-sercx-sercx2customreceivecreate.md">SerCx2CustomReceiveCreate</a> method.

<b>SERCX2_CUSTOM_RECEIVE_CONFIG_INIT</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_CUSTOM_RECEIVE_CONFIG</b>), and sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_CUSTOM_RECEIVE_CONFIG_INIT</b> call.




## -see-also

<a href="..\sercx\nf-sercx-sercx2customreceivecreate.md">SerCx2CustomReceiveCreate</a>



<a href="..\sercx\ns-sercx-_sercx2_custom_receive_config.md">SERCX2_CUSTOM_RECEIVE_CONFIG</a>



 

 


