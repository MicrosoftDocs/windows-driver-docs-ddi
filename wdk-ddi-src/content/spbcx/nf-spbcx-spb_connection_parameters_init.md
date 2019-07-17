---
UID: NF:spbcx.SPB_CONNECTION_PARAMETERS_INIT
title: SPB_CONNECTION_PARAMETERS_INIT function (spbcx.h)
description: The SPB_CONNECTION_PARAMETERS_INIT function initializes an SPB_CONNECTION_PARAMETERS structure.
old-location: spb\spb_connection_parameters_init.htm
tech.root: SPB
ms.assetid: 0E23690B-4AE1-42F1-A53F-FE9A4697DBF2
ms.date: 04/30/2018
ms.keywords: SPB.spb_connection_parameters_init, SPB_CONNECTION_PARAMETERS_INIT, SPB_CONNECTION_PARAMETERS_INIT function [Buses], spbcx/SPB_CONNECTION_PARAMETERS_INIT
ms.topic: function
f1_keywords:
 - "spbcx/SPB_CONNECTION_PARAMETERS_INIT"
req.header: spbcx.h
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
req.irql: Any IRQL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Spbcx.h
api_name:
- SPB_CONNECTION_PARAMETERS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# SPB_CONNECTION_PARAMETERS_INIT function


## -description


The <b>SPB_CONNECTION_PARAMETERS_INIT</b> function initializes an  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/ns-spbcx-_spb_connection_parameters">SPB_CONNECTION_PARAMETERS</a> structure.


## -parameters




### -param Parameters [out]

A pointer to the <b>SPB_CONNECTION_PARAMETERS</b> structure that is to be initialized.


## -returns



None.




## -remarks



Your SPB controller driver must use this function to initialize an <b>SPB_CONNECTION_PARAMETERS</b> structure before passing this structure as an output parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/nf-spbcx-spbtargetgetconnectionparameters">SpbTargetGetConnectionParameters</a> method. This method writes the connection parameters for a target device on the bus to this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/ns-spbcx-_spb_connection_parameters">SPB_CONNECTION_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/nf-spbcx-spbtargetgetconnectionparameters">SpbTargetGetConnectionParameters</a>
 

 

